<link rel="stylesheet" type="text/css" href="style-login.css">
<link href="themes/2/js-image-slider.css" rel="stylesheet" type="text/css" />
<script src="themes/2/js-image-slider.js" type="text/javascript"></script>
<link href="generic.css" rel="stylesheet" type="text/css" />

<body background=back.png>
<form action=register.php method=get>
<p>.
<center><table border=0 width=70%>
<tr><td width=20%><table border=0 bgcolor=white><tr><td width=80% rowspan=3><center><img src=title1.jpg width=100%><td bgcolor=white width=20% align=center><font face='Harrington'>REGISTER</font>
						<p><tr><td bgcolor=white align=center width=1%>
						<input type="text" class="form-control" placeholder="Username" style="width:150;height:40" name="user" required>
						<input type="password" class="form-control" placeholder="Password" style="width:150;height:40" name="pass" required>
						<input type="text" class="form-control" placeholder="Lastname" style="width:150;height:40" name="last" required>
						<input type="text" class="form-control" placeholder="Firstname" style="width:150;height:40" name="first" required>
						<input type="text" class="form-control" placeholder="Middlename" style="width:150;height:40" name="middle" required>
						<input type="text" class="form-control" placeholder="Age" style="width:150;height:40" name="age" required>						
						<tr><td align=center bgcolor=white>
<?php
	if(isset($_GET['save']))
		{
		$a=$_GET['user'];
		$b=$_GET['pass'];
		$c=$_GET['last'];
		$d=$_GET['first'];
		$e=$_GET['middle'];
		$f=$_GET['age'];
		include("myconnection.php");
		
		$query="SELECT * FROM tbluser WHERE user='$a'";
		$res=mysql_query($query);
		$bilang=mysql_num_rows($res);
		
		if($bilang==0)
		{
		$encrypt_password=md5($b);
		$insert="INSERT INTO tbluser VALUES ('$a','$encrypt_password','$c','$d','$e','$f')";
		mysql_query($insert);
		print "<script language=javascript>
		alert('Record Saved');
		window.location='login.php';
		</script>";
		}
		else
			print "<font color=red size=2 face='Lucida Console'>$a already exists</font>";
		}
?>
						<input class="btn" type=submit value="Register" name=save>
						<input class="btn" type=reset value="Clear">
						--------------------------------
						<a href=login.php><img src=HOMIE.jpg width=70%></a></font>
						</table></form>
<tr><td colspan=4 cellspacing=100% cellpadding=100% bgcolor=gray><center>
<marquee bgcolor=gray><font size=5 face='Forte'><?php
echo "Today is  <font color=white> " . date("l - F d, Y");
?></font><font color=gray>__________________</font> Welcome to Bitsy Dynamites! :) <font color=gray>__________________</font>We are the BITS CORPORATION! Feel free to look at our featured BITSY DYNAMITES! </marquee>
<center><tr><td colspan=4>
		<div id="sliderFrame">
        <div id="slider">
            <a href="" target="_blank">
                <img src="images/image-slider-1.jpg" alt="BITSY DYNAMITES" />
            </a>
            <a class="lazyImage" href="images/image-slider-2.jpg" title=""></a>
            <a href=""><b data-src="images/image-slider-3.jpg"></b></a>
            <a class="lazyImage" href="images/image-slider-4.jpg" title=""></a>
        </div>
        <!--thumbnails-->
        <div id="thumbs">
            <div class="thumb">
                <div class="frame"><img src="images/thumb1.jpg" /></div>
                <div class="thumb-content"><p>BITSY DYNAMITES</p>Created for Indulgence!</div>
                <div style="clear:both;"></div>
            </div>
            <div class="thumb">
                <div class="frame"><img src="images/thumb2.jpg" /></div>
                <div class="thumb-content"><p>SATISFACTION GUARANTEED</p>Amazingly satisfying!</div>
                <div style="clear:both;"></div>
            </div>
            <div class="thumb">
                <div class="frame"><img src="images/thumb3.jpg" /></div>
                <div class="thumb-content"><p>TEAM BITS</p>Corporation behind Bitsy Dynamites</div>
                <div style="clear:both;"></div>
            </div>
            <div class="thumb">
                <div class="frame"><img src="images/thumb4.jpg" /></div>
                <div class="thumb-content"><p>VERY AFFORDABLE!</p>Because we want to satisfy all our customers</div>
                <div style="clear:both;"></div>
            </div>
        </div>
        <!--clear above float:left elements. It is required if above #slider is styled as float:left. -->
        <div style="clear:both;height:0;"></div>
    </div>
</table></form># E
