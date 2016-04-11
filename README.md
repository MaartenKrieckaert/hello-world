# hello-world
<!DOCTYPE html>
<html>
<head>
	<title>AJ Cursus</title>
	<meta charset="UTF-8"> 
	
	
	<style>
	img {width:500px}
	.mannetje {width: 100px}
	.blaat {
		border-style: solid; 
		border-radius: 25px; 
		border-color: red;
		}
	hr {height: 10px; background-color: green}
	.graz { float:right;width:42px;height:42px}
	.kaartje {
	width: 500px
	}
	.kaartje:hover {
	cursor: pointer;
	box-shadow: 0 0 10px 0;
	}
	
	</style>
	
	<script>
		var url = "http://geoserver.nl/eurostreets/mapserv.cgi?map=eurostreets/europe.map&LAYERS=europe&FORMAT=image%2Fpng&USERID=37beec27b374&TRANSPARENT=TRUE&SERVICE=WMS&VERSION=1.1.1&REQUEST=GetMap&STYLES=&SRS=EPSG%3A28992&BBOX=[bbox]&WIDTH=1620&HEIGHT=932"
		var bbox = "111047,515732,112408,516515"
		var x = 111047
		var y = 515732
		var Dx = 1000
		var Dy= 1000
		var zoomtekst = document.getElementById("zoomvalue").value
		function zoom(factor){
		Dx = Dx*factor^zoomtekst
		Dy = Dy*factor^zoomtekst
		bbox = (x-Dx) + "," + (y-Dy) +","+ (x+Dx) + "," +(y+Dy)
		document.getElementById("map").src=url.replace("[bbox]",bbox)	
		}

	</script>
</head>	

		
<body>
		Hallo Graziella<br/>
		<hr/>
		<center>
		<img class = "mannetje graz" src= "http://smoelenboek.geodan.nl/erplex/face?doc_id=6577">
		<img class = "mannetje" src= "http://smoelenboek.geodan.nl/erplex/face?doc_id=24224">
		<img class = "mannetje blaat" src= "http://smoelenboek.geodan.nl/erplex/face?doc_id=46426">
		<br/>
		
		<img class = "kaartje" src ="http://geoserver.nl/coolstuff/mapserv.cgi?map=coolstuff/onderwijs.map&LAYERS=kinderopvang&FORMAT=image%2Fpng&USERID=37beec27b374&TRANSPARENT=true&SERVICE=WMS&VERSION=1.1.1&REQUEST=GetMap&STYLES=&SRS=EPSG%3A28992&BBOX=130014.6113341,514888.31400229,151787.4113341,527414.39400229&WIDTH=1620&HEIGHT=932">
		<img id= "map" src ="http://geoserver.nl/eurostreets/mapserv.cgi?map=eurostreets/europe.map&LAYERS=europe&FORMAT=image%2Fpng&USERID=37beec27b374&TRANSPARENT=TRUE&SERVICE=WMS&VERSION=1.1.1&REQUEST=GetMap&STYLES=&SRS=EPSG%3A28992&BBOX=111047.4,515732.16,112408.2,516515.04&WIDTH=1620&HEIGHT=932">
		<br/>
		<input type=button value="Zoom in" onclick=zoom(0.5)> <!-- je kan onclick overal aan hangen ook dus aan imges enzo -->
		</input>
		<input type=button value="Zoom out" onclick=zoom(2)>
		</input>
		<input id = "zoomfactor" type=text value = 1>
		</input> 
		
		<hr/>
		</center>
</body>

</html>


