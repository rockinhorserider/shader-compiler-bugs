# Steps to Reproduce:
1. Open the Chrome browser
2. Navigate to http://htmlpreview.github.io/?https://github.com/mc-imperial/shader-compiler-bugs/blob/master/utils/webgl/webgl_viewer.html
3. Paste the contents of original.frag into the text box
4. Click "Execute"; the rendered image is the expected image for this shader, and should look like original.png
5. Paste the contents of variant.frag into the text box
6. Click "Execute"; you should find that the rendered image is significantly different from the expected image rendered previously

# Expected Results:
Both shaders should render an image that looks like original.png.  This is because the only difference between the .frag files is:

* An unreachable `discard;` statement is added (after a `break;`) in the variant.

# Actual Results:
The shaders render significantly different images, which they should not.

