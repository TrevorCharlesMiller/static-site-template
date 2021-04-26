# Static Site Template

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Introduction
This repository contains a skeleton framework to create static websites using Bootstrap, Font Awesome and Google fonts. It uses Grunt as the main build tool.

## Tech Stack
The libraries/frameworks used are
- Grunt
- Bootstrap
- Sass
- Font Awesome
- Google Fonts

Grunt is used as the main build tool, Bootstrap and Sass as the CSS framework, Font Awesome for icons and Google fonts for fonts.

Templating is used for the header, navigation and footer, thus eliminating code duplication across html files.

CSS and Javascript are concatenated and then minified.

## Build

You will need Node JS v12 or later.

Install dependencies
```
npm install
```

The run Grunt to build the site/
```
grunt
```

This will create a `dist` directory containing html, images, minified css and javascript as well as the `robots.txt` file and the `sitemap.xml` file.