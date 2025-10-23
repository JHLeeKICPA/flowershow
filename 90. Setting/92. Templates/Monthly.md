<%*
function get_week_range(year, month) {
    month = month - 1;
    var monthStart = moment().year(year).month(month).date(1);
    var monthEnd = moment().year(year).month(month).endOf('month');
    var numDaysInMonth = moment().year(year).month(month).endOf('month').date();
    var weeks = Math.ceil((numDaysInMonth + monthStart.day()) / 7);
    var weekRange = [];
    var weekStart = moment().year(year).month(month).date(1);
    var i = 0;
    while (i < weeks) {
        var weekEnd = moment(weekStart);
        if (weekEnd.endOf('week').date() <= numDaysInMonth && weekEnd.month() == month) {
            weekEnd = weekEnd.endOf('week').format('YYYY-MM-DD');
        } else {
            weekEnd = moment(monthEnd);
            weekEnd = weekEnd.format('YYYY-MM-DD')
        }
        var theRange = {
	        'weekNumber': moment(weekStart).format('ww'),
            'weekStart': weekStart.format('YYYY-MM-DD'),
            'weekEnd': weekEnd
        };
        weekRange.push(theRange);
        weekStart = weekStart.weekday(7);
        i++;
    }
    return weekRange;
}
function print_week_range(year, month, range) {
	var i =0, j=0;
	var yoil = ['일', '월', '화', '수', '목', '금', '토']
	for(i = 0; i < range.length; i++) {
		var weekName = 'W'+range[i].weekNumber;
		var dateRange = range[i].weekStart.substr(8, 2) + '일 - ' + range[i].weekEnd.substr(8, 2) + '일';
		var begin = parseInt(range[i].weekStart.substr(8, 2));
		var end = parseInt(range[i].weekEnd.substr(8, 2));
		console.log(dateRange, begin, end);
		tR += '\n> [!tip]- [['+year+'/weekly/'+year+'-'+weekName+'|'+weekName+' ('+dateRange+')]]\n';		
		var cursorDate = moment(range[i].weekStart);
		for(j=begin; j<=end; j++) {			
			tR += ' - '+ cursorDate.format('DD') + '일 ('+cursorDate.format('dd')+') : \n';
			cursorDate = cursorDate.add(1, 'day')
		}
	}
}
var year = tp.file.title.substr(0, 4);
var month = tp.file.title.substr(5, 2);
var weekRange = get_week_range(year, month);
tR += '# ' + year + '년 '+ month + '월 (W'+weekRange[0].weekNumber + ' - W' + weekRange[weekRange.length-1].weekNumber+')\n';
print_week_range(year, month, weekRange);
%>