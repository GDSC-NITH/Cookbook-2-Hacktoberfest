# What are differences between px, dp and sp in Android ?

<br>

When you create the UI layouts of your application, you’re used to define dimensions with units like dp (density-independent pixels), dip or sp (scale-independent pixels). Other units supported are pt (points), px (pixels), mm (millimeters) and in (inches) where as this second kind of units is not recommended because not independent from devices screen pixels.

So, to be clear, Android standard recommend to use the following units :

- **sp** for font-sizes because, like dp, it’s independent pixels but it is also scaled by the user’s font size preference. It is recommend you use this unit when specifying font sizes, so they will be adjusted for both the screen density and the user’s preference.

![](https://i.stack.imgur.com/qPuES.png)

- **dp** for everything else. Observe that dp == dip. Indeed, dip was used in old Android versions and is deprecated. Now, we must use dp.

Advantages of dp are simple to understand but this is what Android documentation tells about dp :

>Using dp units (instead of px units) is a simple solution to making the view dimensions in your layout resize properly for different screen densities. In other words, it provides consistency for the real-world sizes of your UI elements across different devices.

<br>

![](https://miro.medium.com/max/1200/1*us3aVo_yWvoEhvkVFOfgjQ.png)

<br>

## Factors Affecting

### 1. Orientation of the Android Device
The orientation of the screen is seen by the user. This is either landscape or portrait, indicating that the screen’s aspect ratio is broad or tall. Be aware that various devices not only function in different orientations by default but that the orientation might change at runtime when the user spins the device.

### 2. The Density of the screen
The number of pixels inside a physical region of a screen; sometimes abbreviated as dpi (dots per inch). A “low” density screen, for example, contains fewer pixels inside a given physical area than a “normal” or “high” density screen. Android categorizes all real screen densities into six generic densities for ease of use: low, medium, high, extra-high, extra-extra-high, and extra-extra-extra-high.

### 3. Resolution of the Android Device
A screen’s entire amount of physical pixels. When providing support for multiple screens, programs should not be concerned with resolution; instead, they should be concerned with screen size and density, as described by the generic size and density groups.

<br>

## Variations on using different units

!["Difference Table"](https://devstudioonline.com/public/uploads/editor/39_152688660936.PNG)

<br>

## **Conclusion**
Pixels per inch are higher on high-density screens than on low-density ones. As a result, the identical pixel dimensions UI components look larger on low-density screens and smaller on high-density devices. Density-independent pixels, abbreviated as dp (pronounced “dips”), are adaptable units with consistent size on any screen. They offer a versatile approach to fit a design across many platforms. Material UIs employ density-independent pixels to ensure that components appear consistently on displays of varying densities.

<br>

## More Info
[Google Design Documentation](https://m3.material.io/design/layout/pixel-density.html)