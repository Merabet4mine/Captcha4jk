# Captcha4jk
Captcha4jk is a (Kotlin/Java) library for generating ***CAPTCHA*** challenge/answer pairs. 

Captcha4jk is intended to be easy to implement and use sensible defaults, while providing easily-accesssible hooks for customization.



## Using the library

You can download and create the library source code as you like. Or use the ***[jar](https://github.com/Merabet4mine/Captcha4jk/raw/main/c4jk.jar)*** file located above.

- #### Kotlin

```kotlin
val captcha = Captcha().builder(250, 100, "./", Color.white)
        .addLines(10, 10, Color.black)
        .addNoise(false, Color.black)
        .setFont("Arial", 50, Font.BOLD)
        .setText(6, Color.black)
        .build()

captcha.answer // String
captcha.image  // File
```

- #### Java

```java
Captcha captcha = new Captcha().builder(250, 100, "./", Color.white)
        .addLines(10, 10, Color.black)
        .addNoise(false, Color.black)
        .setFont("Arial", 50, Font.BOLD)
        .setText(6, Color.black)
        .build();

captcha.getAnswer(); // String
captcha.getImage();  // File
```

### `Result`

<img src="C:\Users\Administrator\Desktop\captcha.png" alt="captcha"  />



## Methods

- #### builder

  | Name       | Type    | Description                                                  |
  | ---------- | ------- | ------------------------------------------------------------ |
  | width      | Int     | Image (CAPTCHA) width, `default = 250`                       |
  | height     | Int     | Image (CAPTCHA) height, `default = 35`                       |
  | path       | String? | Image (CAPTCHA) path, If the path is **null**, the image will be saved as a temporary file |
  | background | Color?  | Image (CAPTCHA) background color, If the background is **null**, a random RGB color will be used |

  

- #### setFont

  | Name  | Type   | Description                                                  |
  | ----- | ------ | ------------------------------------------------------------ |
  | name  | String | The name of the font used to write the captcha, `default = Arial` |
  | size  | Int    | The font size used in the captcha, `default = 24`            |
  | style | Int    | Font style used in the captcha, `default = Font.BOLD`        |

  

- #### addLines

  | Name       | Type   | Description                                                  |
  | ---------- | ------ | ------------------------------------------------------------ |
  | vertical   | Int    | Number of vertical random lines, `default = 10`              |
  | horizontal | Int    | Number of horizontal random lines, `default = 10`            |
  | width      | Int    | Width of lines, `default = 1`                                |
  | color      | Color? | Lines color, If the color is **null**, a random RGB color will be used |

  **`removeLines()`** : to remove lines.

  

- #### setText

  | Name   | Type       | Description                                                  |
  | ------ | ---------- | ------------------------------------------------------------ |
  | length | Int        | CAPTCHA text length (in letters), `default = 6`              |
  | color  | Color?     | Text color, If the color is **null**, a random RGB color will be used |
  | chars  | List<Char> | The captcha text is randomly generated from a series of characters. The characters used can be customized as using numbers only or only letters. `default = list('a'..'z' + '0'..'9')` |

  

- #### addNoise

  | Name  | Type    | Description                                                  |
  | ----- | ------- | ------------------------------------------------------------ |
  | fill  | Boolean | If you want to fill the image (CAPTCHA) with noises or make it random points, `default = false` |
  | color | Color?  | Noise color, If the color is **null**, a random RGB color will be used |

  **`removeNoises()`** : to remove noises.

  

----

**MIT License**

Copyright (c) 2021 Merabet4mine

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
