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
		div[class*=product] {
			.breadcrumb {
				border-left: 7px solid #ee5c9e;
				margin-bottom: 16px;
				padding-left: 7px;
				.current {
					color: #ee5c9e;
				}
				div{
					&.sprites-more {
						@extend .sprites-more;
						@include sprite-background-position($sprites-sprites, more, 30px, 14px);
					}
				}
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
