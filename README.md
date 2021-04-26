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

Then run Grunt to build the site.
```
grunt
```

This will create a `dist` directory containing html, images, minified css and javascript as well as the `robots.txt` file and the `sitemap.xml` file.

## Create Infrastructure

[Terraform](https://www.terraform.io) is used to create the necessary infrastructure on AWS to deploy the site.

The resources created are 2 AWS S3 buckets, a Route 53 hosted zone and two DNS records. You will need an S3 bucket for 'yourdomain.com' as well as 'www.yourdomain.com' and a DNS record for each.

### Steps to Run

You will need to update your domain name in the terraform variables file: `terraform.tfvars`.

Change into the `terraform` directory and initialize Terraform
```
cd terraform
terraform init
```

Now run plan to see what changes Terraform will apply.
```
terraform plan
```

If you are happy with the changes you can apply them
```
terraform apply
```

You can destroy all the resources created if you no longer need them
```
terraform destroy
```

Note that DNS propagation can take a while so your website might not be reachable through the domain name until the newly created DNS records have propagated through the system. This can take up to 24h hours but usually take about an hour or so.

## Deploy Site
You can use the AWS command line interface to sync the website to your AWS S3 bucket once you have built the website.
```
cd dist
aws s3 sync . s3://yourdomain.com
```