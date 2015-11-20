# TransparentNavigationBar
Simple way to make default navigation bar transparent.

Just add there line to your AppDelegate class's didFinishLaunchingWithOptions function.

	var imageForDefault = self.imageWithColor(UIColor(red: 0.0, green: 0.0, blue: 0.0, alpha: 0.0))
	var imageForCompact = self.imageWithColor(UIColor(red: 0.0, green: 0.0, blue: 0.0, alpha: 0.0)) 
	UINavigationBar.appearance().setBackgroundImage(imageForDefault, forBarMetrics: UIBarMetrics.Default) 
	UINavigationBar.appearance().setBackgroundImage(imageForCompact, forBarMetrics: UIBarMetrics.Compact)


Function I used to make a image is 

	func imageWithColor(color: UIColor) -&gt; UIImage{
		let rect:CGRect = CGRectMake(0, 0, 1, 1);
		UIGraphicsBeginImageContextWithOptions(rect.size, false, 0);
		color.setFill()
		UIRectFill(rect)
		let image: UIImage = UIGraphicsGetImageFromCurrentImageContext()
		return image;
	}