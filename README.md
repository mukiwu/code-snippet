Code Snippet
-----------------------------------
 
### Html mockup
		<article class="index-activity">
			<h2>活動推薦</h2>
			<div class="index-act-image"><a href="#"><img src="images/test_act.png" border="0" /></a></div>
			<section class="box top">
				<div class="label-new">NEW</div>
				<h3><a href="#">聖誕快樂送大家紙膠帶...</a></h3>
				<figure>
					<figcaption>
					<p>基本面強勁，陸客瘋總統府，娶新娘，近兩年最大，李文忠：若蘇要選，敘利亞新憲法草案公投結束，水手官網專訪</p>
					</figcaption>
					<img src="images/test_box.png" border="0" />
				</figure>
			</section>
			<section class="box">
				<div class="label-hot">HOT</div>
				<h3>聖誕快樂送大家紙膠帶...</h3>
				<figure>
					<figcaption>
					<p>基本面強勁，陸客瘋總統府，娶新娘，近兩年最大，李文忠：若蘇要選，敘利亞新憲法草案公投結束，水手官網專訪</p>
					</figcaption>
					<img src="images/test_box.png" border="0" />
				</figure>
				</section>
		</article>
 
### Sass
		div [class*=epg] {
			.title {
				width: 257px;
				position: relative;
			}
			.breadcrumb, .title {
				border-left: 7px solid #e46941;
				margin: 0;
				padding: 0 0 0 7px;
				.current {
					color: #e46941;
				}
			}
			.entry {
				border-bottom: 1px solid #fafafa;
				@include middle_out;
			}
		}
		
		button {
			border: none;
			color: #fff;
			padding: 5px 12px;
			margin: 0 10px 0 0;
			@include text-shadow(1px 1px 1px rgba(100,100,100, .5));
			@include box-shadow(0 1px 1px rgba(0,0,0, .8));
			&[class="add"] {
				background: #ff5b26;
			}
			&[class="invite"] {
				background: #a5938f;
			}
		}
 
### jQuery
 
		$(function(){
			function colorChange($this){
			$this.addClass("active").css("background",$this.data("color")).parent().css("border-bottom-color", $this.data("color"));
				$this.siblings().removeClass("active").removeAttr("style");
			}

			$(".tab-menu li").mouseenter(function(){
				colorChange($(this));
				_clickTab = $(this).find("a").attr("href");
				$(_clickTab).stop(false, true).fadeIn().siblings().hide();
			});

			$(".tab-menu li").click(function(){
				colorChange($(this));
				$(this).mouseleave(function(e){
					$(e.currentTarget).unbind("mouseleave");
				})
			})
		});
