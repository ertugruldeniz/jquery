<!DOCTYPE html>
<html>
<head>
	<title>Jquery Ders1</title>
    <style>
        .eklenecekclass{
            width: 100px;
            height: 100px;
            background-color: red;
            position: relative;
            -webkit-animation-name: example; /* Safari 4.0 - 8.0 */
            -webkit-animation-duration: 4s; /* Safari 4.0 - 8.0 */
            animation-name: example;
            animation-duration: 4s;
        }
        /* Standard syntax */
        @keyframes example {
            0%   {background-color:red; left:0px; top:0px;}
            25%  {background-color:yellow; left:200px; top:0px;}
            50%  {background-color:blue; left:200px; top:200px;}
            75%  {background-color:green; left:0px; top:200px;}
            100% {background-color:red; left:0px; top:0px;}
        }
        .i{
            color: aqua;
        }
        .selected{
            text-decoration: underline;
            color: red;
            background-color:yellow;
        }
        .selected1{
            color:chocolate;
            background-color:chartreuse;
        }
        .find{
            background-color:deeppink;
        }
        .slice{
            background-color: coral;
            font-size: 1.2em;
        }
        #css{
            width:70px; height:50px; float:left;
            margin:5px; background:red; cursor:pointer;
        }
        .div{ margin:10px;padding:12px; border:2px solid #666; width:60px;}
    </style>
	<script type="text/javascript" src="jquery.js"></script>
	<script type="text/javascript">
		
		$(document).ready(function(){
            $(".myDiv").click(function () {
                alert("Buraya Tıkla Yazan Yazıya Tıklandı");
                document.write("Hello");
            });
            $(".renkdegistir").hover(function () {
                $("p").css("background-color", "yellow");
                $("body").css("background-color", "purple");
            });
            var title = $("em").attr("title"); //attr etiketlerin özellikklerine ulaşmaya yarar
            $("#divid").text(title);
            //Attr ayrıntılı kullanım
            $("#resimdegistir").click(function () {
                $("#resim").attr("src","img/jq-min.png"); //resi yolu değiştirildi
                $("#resim").attr("alt","Alt etiketi değişti"); //resim alt etiketi değiştirildi
                //Yeni bir class da ekleme işlemi addClass
                //removeClass ile class silinebilir
                $("#addclass").addClass("eklenecekclass");
                $("#addclass").toggleClass("i");
            });
                //BELİRLİ BİR VERİYİ SEÇME
               $("li").eq(2).addClass("selected");
               $("li").filter(".middle").addClass("selected1");
               //Bir etiket içerisinde bulunan başka etiketleri arama işlemi find
                $("p").find("span").addClass("find");
                //li içerisinde eleman arama
                    $("li").click(function () {
                    if ($(this).is(":first-child")) { //ul içerisindeki ilk li
                        $("p").text("This is list item 1");
                    } else if ($(this).is(".middle0,.middle1")) {
                        $("p").text("This is middle class list");
                    } else if ($(this).is(":contains('item 5')")) {
                        $("p").text("It's 5th list");
                    }
                });
                    //slice kullanıc slice(start,end)
                $(".slice li").slice(2, 5).addClass("slice");
                //css Kullanımı
                $("div#css:first").width(100);
                $("div#css:first").css("background-color", "blue");
                //remove komutu tagları kaldırır.
                $(".div").click(function () {
                    $(".div").remove( );
                });
            $('.divevent').bind('click', function( event ){
                alert('Hi there!');
            });
		});
	</script>

</head>
<body>
<em title = "Burası em etikenin başlığı">Bu bir paragraf.</em>
<a href="void:javascript(0)" ><div class="myDiv">Buraya Tıkla</div></a>
<p class="renkdegistir">Üzerime gel ve arkaplan rengini değişsin</p>
<div id="divid"> </div>

<img id="resim" src="img/php.png" alt="Bu bir php resmi">
<button id="resimdegistir"> Tikla resmi değiştir</button>
<div id="addclass">Bu div kutuya dönüşecek</div>


<div>
    <ul>
        <li>list item 1</li>
        <li>list item 2</li>
        <li>list item 3</li>
        <li>list item 4</li>
        <li>list item 5</li>
        <li>list item 6</li>
    </ul>
</div>

<div>
    <ul>
        <li class = "middle">list item 1</li>
        <li class = "top">list item 2</li>
        <li class = "middle">list item 3</li>
        <li class = "middle">list item 4</li>
        <li class = "bottom">list item 5</li>
        <li class = "bottom">list item 6</li>
    </ul>
</div>

<div class = "divevent" style = "background-color:blue;">ONE</div>
<div class = "divevent" style = "background-color:green;">TWO</div>
<div class = "divevent" style = "background-color:red;">THREE</div>

<p>
    <span>Span1</span>
    <span>Span2</span>
    <span>Span3</span>

</p>

<div>
    <ul class="slice">
        <li class = "top0">list item 1</li>
        <li class = "top1">list item 2</li>
        <li class = "middle0">list item 3</li>
        <li class = "middle1">list item 4</li>
        <li class = "bottom0">list item 5</li>
        <li class = "bottom1">list item 6</li>
    </ul>
</div>


        <div id="css"></div>
        <div id="css">d</div>
        <div id="css">d</div>
        <div id="css">d</div>
        <div id="css">d</div>
<br><br><br><br>
<div class = "div" style = "background-color:blue;"></div>
<div class = "div" style = "background-color:green;"></div>
<div class = "div" style = "background-color:red;"> Bu kutuları silmek için tıkla</div>



</body>
</html>
