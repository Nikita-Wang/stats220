# Welcome π₯³

Hello! This is my STATS220 website π§Έ

## About me π

- I am a Chinese girl and I'm now reading for a [data science degree](https://www.auckland.ac.nz/en/study/study-options/find-a-study-option/data-science.html) π at the [University of Auckland](https://www.auckland.ac.nz/en.html).

- I **LOVE** dogs π₯° (especially the golden retriever)

- I have a series of interests, such as 
     1. *EATING EATING EATING* π
     2. keeping a diary
     3. reading π & watching documentaries π
     4. learning different languages 
     5. playing the piano πΉ & listening to the music π§
     6. πΈπ΄π»ππ»ββοΈβΈπ‘π¬...... 


## I learned to make my own meme π

The meme below was made by me using the R package [{magick}](https://cran.r-project.org/web/packages/magick/vignettes/intro.html).

![](my_meme.png)

### More about my meme

1. Since I really love golden retriever, I think it is awesome to use the pictures of golden retriever to be my first meme π
2. I found the meme I liked and make the caption for each picture by myself π
3. Use the `R` code below to creat my own meme βπ»

Here are the codes:

```r
library(magick)


# 3 pictures used in meme
exciting_dog <- image_read("https://www.meme-arsenal.com/memes/3628e4f08adb608f0fb992baf7030062.jpg")%>%
  image_scale(450)

studing_dog <- image_read("https://uploads.dailydot.com/a6a/ed/775fb3fce3a1a902.jpg?auto=compress&fm=pjpg&ixlib=php-3.3.0")%>%
  image_scale(450)

resting_dog <- image_read("https://uploads.dailydot.com/61b/68/711c2808700a1bdd.jpg?auto=compress&fm=pjpg&ixlib=php-3.3.0")%>%
  image_scale(450)


# 3 texts used in meme
holiday_text <- image_blank(width = 450,
                            height = 450,
                            color = "#000000") %>%
  image_annotate(text = "Holiday\nstarts\nTODAY!",
                 color = "#FFFFFF",
                 size = 75,
                 font = "Impact",
                 gravity = "center")

others_text <- image_blank(width = 450,
                           height = 450,
                           color = "#000000") %>%
  image_annotate(text = "Other people\nduring\nholiday",
                 color = "#FFFFFF",
                 size = 75,
                 font = "Times",
                 gravity = "center")

me_text <- image_blank(width = 450,
                       height = 450,
                       color = "#000000") %>%
  image_annotate(text = "ME\nduring\nholiday",
                 color = "#FFFFFF",
                 size = 75,
                 font = "Times",
                 gravity = "center")


# making each row by combining each picture with its corresponding text
first_row <- c(exciting_dog, holiday_text) %>%
  image_append()

second_row <- c(studing_dog, others_text) %>%
  image_append()

final_row <- c(resting_dog, me_text) %>%
  image_append()


# making the whole thing!
my_meme <- c(first_row, second_row, final_row) %>%
  image_append(stack = TRUE)


# save the meme as an image file called 'my_meme.png' 
image_write(my_meme, "my_meme.png")
  
```
