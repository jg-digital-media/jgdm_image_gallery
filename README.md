# jgdm_image_gallery  - Last Update  - 16/02/2022 11:20


## Setup for a static image gallery website

Depending on the animation style you want to import, there are different gallery animations available. They are stored in separate Sass Partial files.

+ ```_no.scss```
+ ```_v1.scss```

Simply switch the required ```@import``` directive as list in the `sass.scss` file in this project.

## no.scss 

+ With no opacity, visibility or display styling or style transitioning applied.

```css
    li.gallery_item {
        width: 20px;
        width: 30%;
        display: inline-block;
        margin: 10px 1%;
        position: relative;

        @media(max-width: $breakpoint-md) {
            width: 47%;

        }

        @media(max-width: $breakpoint-xs) {
            width: 90%;
            display: block;
            margin: 0 auto;
            position: relative;

        }

        img {
            width: 100%;
        }

        div.caption {
            position: relative;
            background: black;
            /* top: -29px; */
            bottom: 35px; 

            p {
                position: relative;
                /* background: black; */
                color: white;
                font-size: 10px;
                width: 90%;
                /* bottom: 25px; */
                height: 25px;
                height: 100%;
                padding: 10px 5px;
                /* margin-left: 5px; */
                left: 30px;
            }
        }    
    

}
```


## v1.scss

+ With relative positioning and opacity properties, there is animated fade transitioning included to the captioning of images on mouse hover.

```css
    li.gallery_item {
        width: 20px;
        width: 30%;
        display: inline-block;
        margin: 10px 1%;
        position: relative;

        @media(max-width: $breakpoint-md) {
            width: 47%;

        }

        @media(max-width: $breakpoint-xs) {
            width: 90%;
            display: block;
            margin: 0 auto;
            position: relative;

        }

        img {
            width: 100%;

            & + div.caption {
                visibility: hidden;
                opacity: 0;
                transition: opacity .6s;
            }
            
            &:hover + div.caption {
                //display: none;
                visibility: visible;
                opacity: 1;
                transition: opacity .6s;


                &:hover {
                    //display: block;
                    visibility: hidden;
                    opacity: 0;
                    transition: opacity .6s;
                }

            }
        }

        div.caption {
            position: relative;
            background: black;
            /* top: -29px; */
            bottom: 35px; 

            p {
                position: relative;
                /* background: black; */
                color: white;
                font-size: 10px;
                width: 90%;
                /* bottom: 25px; */
                height: 25px;
                height: 100%;
                padding: 10px 5px;
                /* margin-left: 5px; */
                left: 30px;
            }
        }    
    

    }
```
