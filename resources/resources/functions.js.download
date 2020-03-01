function loadSettings() {
	$.each(localStorage, function(key, value){
		$('td#'+key).addClass(value);
	})
};

// set conqitem
function setConq(i) {
	if(!$('#conq'+i).hasClass('done')) {
		$('#conq-'+i).addClass('done');
		localStorage.setItem('conq-'+i, 'done');
	}
}

// unset conqitem
function unsetConq(i) {
	if($('#conq-'+i).hasClass('done')) {
		$('#conq-'+i).removeClass('done');
		localStorage.setItem('conq-'+i, 'not');
	}
}

// set sjitem
function setSJ(i, j) {
	if(!$('#td-sj'+i+''+j).hasClass('done')) {
		$('#td-sj'+i+''+j).addClass('done');
		localStorage.setItem('td-sj'+i+j, 'done');
	}
}

// unset sjitem
function unsetSJ(i, j) {
	if($('#td-sj'+i+''+j).hasClass('done')) {
		$('#td-sj'+i+''+j).removeClass('done');
		localStorage.setItem('td-sj'+i+j, 'not');
	}
}

function resetAll() {
	var abc = "abcdefghijklmnopqrstuvwxyz";
	for(i=0; i<10; i++) {
		unsetConq(abc.charAt(i));
	}
	for(i=1; i<=9; i++) {
		for(j=0; j<12; j++) {
			unsetSJ(i, abc.charAt(j));
		}
	}
}

// check completed chapters
function checkComplete() {
	var criterion = [0, 9, 11, 11, 12, 10, 10, 8, 8, 6];
	var current = 1;
	while($('td.sjitem.done.cat'+current).length == criterion[current]) {
		$('#td-sj'+current+'m, #complete'+current).removeClass('current');
		$('#td-sj'+current+'m, #complete'+current).addClass('complete');
		$('#complete'+current).html('Complete!');
		current++;
	}
	
	// mark the current
	if(current<10) {
		$('#td-sj'+current+'m, #complete'+current).addClass('current');
		$('#complete'+current).html('Current');
	}
	
	// mark all above as incomplete
	for(i=current+1; i < 10; i++) {
		$('#td-sj'+i+'m, #complete'+i).removeClass('current');
		$('#td-sj'+i+'m, #complete'+i).removeClass('complete');
		$('#complete'+i).html('');
	}
}
