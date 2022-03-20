## Welcome to my assignment1 website! 



I'm a data science student at the [University of Auckland](https://unidirectory.auckland.ac.nz/profile/a-fergusson).

![](meme.png)

Below is a meme I made using the R package [{magick}](https://cran.r-project.org/web/packages/magick/vignettes/intro.html).



A short desccribtion about  the assignment:
The picture is about Bikini Bottom

If you want to learn more, you can check:(https://zh.wikipedia.org/wiki/%E6%B5%B7%E7%B6%BF%E5%AF%B6%E5%AF%B6)



```
library(magick)
bs<-image_blank(width = 622,height = 622,color = "#000000") %>%
  image_annotate(text = "Bikini Bottom",
                 color = "#0066ff",
                 size = 40,
                 font = "Impact",
                 gravity = "center")
bs
sb<-image_read("https://bkimg.cdn.bcebos.com/pic/2fdda3cc7cd98d10bfd396682c3fb80e7bec9060?x-bce-process=image/crop,x_0,y_0,w_395,h_557/resize,m_lfit,h_780,limit_1/quality,Q_70/format,f_auto")
sb<-image_annotate(sb, "SpongeBob!", color = "black", size = 30,location = "+100+30")
sb<-image_scale(sb, "x622")
print(sb)

ps<-image_read("https://bkimg.cdn.bcebos.com/pic/902397dda144ad345982ae0fe8f01bf431adcaef2fa3?x-bce-process=image/watermark,image_d2F0ZXIvYmFpa2U5Mg==,g_7,xp_5,yp_5/format,f_auto")
ps<-image_annotate(ps, "Patrick Star!", color = "black", size = 30,location = "+270+30")
print(ps)
meme<-c(sb, ps,bs) %>%
  image_append(stack = FALSE) %>%
  image_scale(1000)
meme
image_write(meme, "my_meme.png")
```
