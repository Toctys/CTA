CTA
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8">
	<link rel="stylesheet" href="http://code.jquery.com/mobile/1.4.2/jquery.mobile-1.4.2.min.css" />
	<script src="http://code.jquery.com/jquery-1.9.1.min.js"></script>
	<script src="http://code.jquery.com/mobile/1.4.2/jquery.mobile-1.4.2.min.js"></script>
	<script src="c:\users\steven\documents\pinkline\loops.js"></script>
	<meta name="veiwport" content="width= device-width, initial-scale=1, maximum-scale=1"/>
</head>
<body>
<header data-role="header">
<h1>Cta Pink Line</h1>
</header>
<article data-role"content">
	<input type="search" id="query"/>
	<a data-inline="true" data-role="button" href="#" onClick="javascript:getStations()"><span>Get Stations</span></a>
	<ul data-role="listview" data-inset"true" id="stations">
	</ul>
</article>
<footer data-role="footer" data-position="fixed">
	<nav data-role="navbar">
		<ul>
			<li><a href="#"> Home</a></li>
			<li><a href="#"> Info</a></li>
		</ul>
	</nav>
</footer>
<script>
	$(document).ready(function(){
		getStations =function(){
			$("#stations").html("");
			$.getJSON("http://data.cityofchicago.org/resource/8pix-ypme.json?",function(data){
				$.each(data, function(index, item){
					station_name = item.station_name;
					stop_name = item.stop_name;
					$("#stations").append('<li><a href="#"><h3>'+station_name+'</h3><p>'+stop_name+'</p></a></li>');
			$("#stations").listview();
			$("#stations").listview("refresh");
				});
			});
		}
	});
</script>
</body>
</html>
