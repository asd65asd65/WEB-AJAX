# WEB

<h2>AJAX</h2>
<hr/>
<h3>t1 更新部分網頁內容</h3>
<p>為了安全性，不建議直接讓別人透過瀏覽器直接訪問主機內的文件。</p>
<oi>
<li>t1.html</li>
<li>info.txt</li>
</oi>

<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>t1</title>
<script>
function loadXMLDoc()
{
	var xmlhttp;
	if (window.XMLHttpRequest)
	{
		//  IE7+, Firefox, Chrome, Opera, Safari 瀏覽器請求
		xmlhttp=new XMLHttpRequest();
	}
	else
	{
		// IE6, IE5 瀏覽器請求
		xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
	}
	xmlhttp.onreadystatechange=function()
	{
		if (xmlhttp.readyState==4 && xmlhttp.status==200)
		{
			document.getElementById("Div_1").innerHTML=xmlhttp.responseText;
		}
	}
	xmlhttp.open("GET","info.txt",true);
	xmlhttp.send();
}
</script>
</head>
<body>

<div id="Div_1"><h2>使用 AJAX 修改该文本内容</h2></div>
<button type="button" onclick="loadXMLDoc()">更改内容</button>

</body>
</html>
