The same height of the Divi blog grid
---
Add a Custom CSS Class to the Blog Module - pa-blog-equal-height

We will add the script and css using the CODE module to the page with blog articles, so that the script does not load unnecessarily even on pages where it is not needed.

```js
(function ($) {
		var pa_equalize_button_height = "true";

		if (pa_equalize_button_height == "false") {
			function pa_equalize_blog_post_height(blog) {
				var articles = blog.find('article');
				var heights = [];

				articles.each(function () {
					var height = 0;
					height += ($(this).find('.et_pb_image_container, .et_main_video_container').length != 0) ? $(this).find('.et_pb_image_container, .et_main_video_container').outerHeight(true) : 0;
					height += $(this).find('.entry-title').outerHeight(true);
					height += ($(this).find('.post-meta').length != 0) ? $(this).find('.post-meta').outerHeight(true) : 0;
					height += ($(this).find('.post-content').length != 0) ? $(this).find('.post-content').outerHeight(true) : 0;

					heights.push(height);
				});

				var max_height = Math.max.apply(Math, heights);

				articles.each(function () {
					$(this).height(max_height);
				});
			}
		} else {
			function pa_equalize_blog_post_height(blog) {
				var articles = blog.find('article');
				var heights = [];
				var btnheights = [];

				articles.each(function () {
					var height = 0;
					var btnheight = 0;
					var basebtnmargin = 20;

					height += ($(this).find('.et_pb_image_container, .et_main_video_container').length != 0) ? $(this).find('.et_pb_image_container, .et_main_video_container').outerHeight(true) : 0;
					height += $(this).find('.entry-title').outerHeight(true);
					height += $(this).find('.post-meta').outerHeight(true);
					height += $(this).find('.post-content').outerHeight(true);

					btnheight += ($(this).find('.et_pb_image_container, .et_main_video_container').length != 0) ? $(this).find('.et_pb_image_container, .et_main_video_container').outerHeight(true) : 0;
					btnheight += $(this).find('.entry-title').outerHeight(true);
					btnheight += $(this).find('.post-meta').outerHeight(true);
					btnheight += $(this).find(".post-content p").outerHeight(true);
					btnheight += basebtnmargin;

					heights.push(height);
					btnheights.push(btnheight);

				});

				var max_height = Math.max.apply(Math, heights);
				var max_btn_height = Math.max.apply(Math, btnheights);

				articles.each(function () {
					$(this).height(max_height);

					var eachheight = 0;
					var eachbasebtnmargin = 20;
					eachheight += ($(this).find('.et_pb_image_container, .et_main_video_container').length != 0) ? $(this).find('.et_pb_image_container, .et_main_video_container').outerHeight(true) : 0;
					eachheight += $(this).find('.entry-title').outerHeight(true);
					eachheight += $(this).find('.post-meta').outerHeight(true);
					eachheight += $(this).find(".post-content p").outerHeight(true);
					eachheight += eachbasebtnmargin;

					var requiredbtnmargin = (max_btn_height - eachheight) + eachbasebtnmargin;
					$(this).find(".more-link").css("margin-top", requiredbtnmargin + "px");
				});
			}
		}
    
		$(document).ready(function () {
			$(window).resize(function () {
				if ($(this).width() >= 768) {

					$(".pa-blog-equal-height article").each(function () {
						$(this).removeClass("pa-auto-height");
						$(this).find(".more-link").removeClass("pa-auto-margin");
					})
					$('.pa-blog-equal-height').each(function () {
						pa_equalize_blog_post_height($(this));
					});

					$('.pa-blog-equal-height').each(function () {
						var pa_blog = $(this);

						pa_equalize_blog_post_height(pa_blog);

						var observer = new MutationObserver(function (mutations) {
							pa_equalize_blog_post_height(pa_blog);
						});

						var config = {
							subtree: true,
							childList: true
						};

						observer.observe(pa_blog[0], config);
					});

					$(document).ajaxComplete(function () {
						$('.pa-blog-equal-height').imagesLoaded().then(function () {
							$('.pa-blog-equal-height').each(function () {
								pa_equalize_blog_post_height($(this));
							});
						});
					});

					$.fn.imagesLoaded = function () {
						var $imgs = this.find('img[src!=""]');
						var dfds = [];

						if (!$imgs.length) {
							return $.Deferred().resolve().promise();
						}

						$imgs.each(function () {
							var dfd = $.Deferred();
							dfds.push(dfd);
							var img = new Image();

							img.onload = function () {
								dfd.resolve();
							};

							img.onerror = function () {
								dfd.resolve();
							};

							img.src = this.src;
						});

						return $.when.apply($, dfds);
					}
				} else {
					$(".pa-blog-equal-height article").each(function () {
						$(this).addClass("pa-auto-height");
						$(this).find(".more-link").addClass("pa-auto-margin");
					})
				}
			});
		});
	})(jQuery); 
``` 


```css
.pa-blog-equal-height .pa-auto-height {
    height: auto !important;
}

.pa-blog-equal-height .pa-auto-margin {
    margin-top: 20px !important;
}
```