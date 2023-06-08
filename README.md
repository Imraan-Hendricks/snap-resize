# SnapResize

SnapResize is a lightweight client-side image resizing NPM package that allows you to easily resize images before uploading them to the server. It provides a simple and efficient solution for adjusting image dimensions, aspect ratios, and quality.

### Installation

Install SnapResize using npm:

```shell
npm install @imraan-hendricks/snap-resize
```

### Usage

Here's an example of how to use SnapResize in your JavaScript/TypeScript code:

```typescript
import { snapResize } from '@imraan-hendricks/snap-resize';

async function handleFileOnChange(e) {
  const files = e.currentTarget.files;
  if (!files || files.length === 0) return;
  try {
    const file = files[0];
    const options = { aspectRatio: '1:1', height: 400, quality: 0.92 };
    const { original, result } = await snapResize(file, options);
    // `original` contains the details of the original image
    // `result` contains the details of the resized image
  } catch (error) {
    alert(error.message);
  }
}
```

### Benefits of Image Resizing

Resizing images before uploading them to the server offers several benefits:

- **Consistency:** By resizing images on the client side, you ensure consistent dimensions and aspect ratios across different devices and platforms. This helps maintain visual integrity and avoids distorted or stretched images.
- **Performance:** Uploading large images can impact the performance of your web application or website. By resizing images before uploading, you reduce the file size, leading to faster upload times and improved overall performance.
- **Bandwidth Optimization:** Smaller image sizes result in reduced bandwidth usage, making it beneficial for users with limited internet connectivity or mobile data plans. Resizing images helps optimize bandwidth consumption and provides a smoother user experience.
- **Storage Efficiency:** Storing and serving large images can consume significant storage space and resources on your server. Resizing images before uploading allows you to store smaller-sized images, optimizing storage efficiency and reducing hosting costs.
- **Improved User Experience:** Users often prefer websites or applications that load quickly and provide a seamless experience. By reducing the size of images before uploading, you enhance the user experience by minimizing loading times and improving overall responsiveness.

### API

```typescript
snapResize(originalFile, options, minHeight);
```

Resizes an image based on the provided options.

- **originalFile:** The original image file (type: File).
- **options:** An object containing the resizing options:
  - **aspectRatio:** The desired aspect ratio of the resized image (format: 'width:height').
  - **height:** The desired height of the resized image.
  - **quality (optional):** The desired image quality (range: 0 to 1, default: 0.92).
- **minHeight (optional):** The minimum height (in pixels) of the image to avoid excessive compression (default: 10).

Returns a Promise that resolves to an object containing the following properties:

- **original:** An object containing the details of the original image:
  - **base64:** The base64-encoded representation of the original image.
  - **dimensions:** An object containing the width and height of the original image.
  - **file:** The original image file (type: File).
- **result:** An object containing the details of the resized image:
  - **base64:** The base64-encoded representation of the resized image.
  - **dimensions:** An object containing the width and height of the resized image.
  - **file:** The resized image file (type: File).

For more detailed information, advanced usage, and customization options, please refer to the [documentation](https://github.com/Imraan-Hendricks/snap-resize).

### Contributing

Contributions are always welcome! If you encounter any issues, have suggestions, or want to contribute improvements, please open an issue or submit a pull request in the [Github repository](https://github.com/Imraan-Hendricks/snap-resize).

### Support

If you have any questions, issues, or need assistance, please feel free to reach out to our support team at support@imraanhendricks.com. We are here to help and will get back to you as soon as possible.

### License

This project is licensed under the [MIT License](https://github.com/Imraan-Hendricks/snap-resize/blob/main/LICENSE).
