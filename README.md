# Simple Clicker

A minimalist web-based click counter that allows users to track the number of times they click a button. The application is built with HTML, CSS, and JavaScript, and is designed to render well on both desktop and mobile devices. The counter can be incremented by clicking the "Click Me!" button, and it can be reset using the "Reset" button.

## Features

- **Simple and Intuitive Interface**: The application consists of two buttons, one for incrementing the counter and one for resetting it to zero.
- **Responsive Design**: The page is fully responsive and adapts to different screen sizes, making it easy to use on both desktop and mobile devices.
- **Fast and Lightweight**: The app uses plain HTML, CSS, and JavaScript, without any external libraries or frameworks, ensuring fast performance.

## Demo

You can see a live demo of the Simple Clicker [here](http://simple-clicker-magoulet.s3-website-us-west-2.amazonaws.com/).

## Code Overview

### HTML Structure

- The `div` with `id="countDisplay"` is used to display the current count.
- The `button` elements trigger JavaScript functions to either increment the counter or reset it.

### CSS Styling

- The page is styled using basic CSS, with a flexbox layout to center the content vertically and horizontally.
- Buttons are styled with distinct colors: green for incrementing and red for resetting, making them easy to differentiate.

### JavaScript Logic

- The counter is stored in the `count` variable and updated each time the user clicks the "Click Me!" button.
- The `incrementCounter()` function increments the counter and updates the display.
- The `resetCounter()` function resets the counter to zero.

## How to Use

1. Clone or download the repository.
2. Open the `index.html` file in any web browser.
3. Click the "Click Me!" button to increment the counter.
4. Use the "Reset" button to reset the count to zero.

### Step-by-Step Guide to Set Up S3 Static Website Hosting

#### 1. **Create the S3 Bucket with Public Access**

Run the following command to create a new S3 bucket (replace `<bucket-name>` with your desired bucket name and `<region>` with your AWS region, like `us-west-2`):

```bash
aws s3 mb s3://<bucket-name> --region <region> --profile default
```

#### 2. **Enable Static Website Hosting**

Once the bucket is created, you need to configure it to serve a static website. Run the following command to set the bucket’s website configuration (replace `<bucket-name>` with your actual bucket name):

```bash
aws s3 website s3s
```

This command sets `index.html` as the default document (you can change it if your site has a different main file) and `error.html` as the error page.

#### 3. **Set Bucket Policy for Public Access**

In order for the bucket to serve content to the public, you need to modify the bucket's policy to allow public access to the files.

Here is a good bucket policy JSON file  (replace `<bucket-name>` with your actual bucket name):

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::<bucket-name>/*"
    }
  ]
}
```

Then apply this policy to the bucket using the method of your choice.

#### 4. **Upload Your Website Files**

You can use the `Makefile` to deploy your website as we set up earlier, or run the following command to manually upload your files to the bucket:

```bash
aws s3 sync . s3://<bucket-name> --profile default
```

#### 5. **Access the Website**

After setting up the bucket for static hosting, your website will be available at the following URL:

```
http://<bucket-name>.s3-website-<region>.amazonaws.com/
```

For example, if your bucket is named `simple-clicker-magoulet` and hosted in `us-west-2`, the URL would be:

```
http://simple-clicker-magoulet.s3-website-us-west-2.amazonaws.com/
```

### Optional: **Set Up a Custom Domain**

If you have a custom domain (like `mydomain.com`), you can configure it to point to your S3 bucket using **Amazon Route 53** or another DNS provider.

1. **Update Route 53 DNS (or your domain provider)**
   - Create an **Alias Record** in Route 53 that points to your S3 bucket.
   - In the Route 53 Console, choose "Alias to S3 website endpoint" when creating the record.

2. **Set up SSL for HTTPS**
   - If you want HTTPS support, you’ll need to use **Amazon CloudFront** as S3 static websites do not directly support HTTPS.

This setup will allow you to serve a static website directly from your S3 bucket while keeping it publicly accessible.

## License

This project is licensed under the MIT License. Feel free to use, modify, and distribute this code as needed.

---

Happy clicking! 🚀
