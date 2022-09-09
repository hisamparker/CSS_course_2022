# Notes on accessibility
While doing this course I tried to do research about accessibility for every section alongside the course materials which did not touch on accessibility at all really.

## Text
To make the internet more accessible to users with low vision, we need to think about how text is displayed. Contrast, size/scalability of size, font style, and white space are all important considerations.

### Text—Contrast
Text has to follow a [contrast ratio](https://css-tricks.com/accessible-font-sizing-explained/#:~:text=Secondly%2C%20there%E2%80%99s-,contrast,-.%20This%20is%20why) of at least 4.5:1, with the exception of a large-scale text that should have a contrast ratio of at least 3:1.

Web aim has a nice [contrast checker tool](https://webaim.org/resources/contrastchecker/) for making sure your contrast is accessible to all users.

### Text—Font size
There's no one-size-fits-all for font size because different alphabets will require different guidelines because simple characters are more readable at smaller font sizes, complex characters are not.

This is why the [WCAG](https://www.w3.org/WAI/standards-guidelines/wcag/) specifies using contrast instead of size.

Because a browser’s default styles are accessible, we can use them to build an accessible font size strategy.

#### ***Think about proportions, not size***
The browser first loads default styles, the “User Agent stylesheet”, then those cascade to the styles we define, and they both cascade and get overwritten by the user’s styles.

Users with low vision can change the default font size in their browser settings. We don't want to make it harder for them to do this as that would result in a less accessibile experience for these users. We want to provide flexibility because we don't know the exact size, language, or font family that our content will end up displayed in.

Our job is to control proportions.

We can use CSS relative units to make our content reactive to it's environment, so that we maintain proportionality withough hindering the user's accessibility requirements.

The [WCAG recommends using em units to define font size](https://www.w3.org/TR/WCAG20-TECHS/C14.html). We can user rems and ems to define size proportionally for basically every property.

#### ***Do's, don'ts, and maybes***
* Do rely on the browsers default size as a baseline
* Don't set a default size on the root document
* Maybe reset the header styles to 1rem as this 




### Text—Font family
We don’t fully control the font-family property, either. The content might be translated, the custom font family might fail to load, or it might even be changed. For example, [OpenDyslexic](https://gumroad.com/l/OpenDyslexic) is a typeface created to increase readability for readers with dyslexia. In some situations, we may even explicitly allow [switching between a limited set of fonts](https://dev.to/devteam/new-feature-display-configuration-sans-serif-fontsnight-mode-beta-23o0).

Therefore, when defining fonts, we have to avoid hindering the ability of a user or a device to change our styles and let go of assumptions: we just don’t know where our content is going to land and we can’t be sure about the exact size, language, or font that’s used to display content.

