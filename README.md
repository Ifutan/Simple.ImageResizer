Simple C# ImageResizer library using wpf classes

Available on NuGet:
PM> Install-Package Simple.ImageResizer

Usage:
<pre>
ImageResizer.ImageResizer resizer = new ImageResizer.ImageResizer(@"c:\path\to\image.jpg");

// resize to 400 px, jpg quality 90
var byteArray1 = resizer.Resize(400, ImageEncoding.Jpg90);

// resize to 400 px, height 200, ScaleToFill, png
var byteArray2 = resizer.Resize(400, 200, true, ImageEncoding.Png);

// resize to 400 px, height 200, ScaleToFit, gif
var byteArray3 = resizer.Resize(400, 200, false, ImageEncoding.Gif);

// save last resized image to file
resizer.SaveToFile(@"c:\path\to\image_resized.gif");
</pre>

Or
<pre>
public ActionResult Upload(HttpPostedFileBase file)
{
      var imageResizer = new ImageResizer.ImageResizer(file.InputStream.ToByteArray());
      imageResizer.Resize(800, ImageEncoding.Jpg100);
      imageResizer.SaveToFile(Path.Combine(Server.MapPath("~/upload"), file.FileName));
      return View();
}
</pre>