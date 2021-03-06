# SWRevealViewController

A UIViewController subclass for revealing a rear (left and/or right) view controller behind a front controller, inspired by the Facebook app, done right!

## Features

* A Reveal view controller implemented using view controller containment.
* API easier than a UINavigationController.
* Support for any combination of left/right rear controllers.
* Correct handling of appearance methods on its child controllers that you can rely on.
* Correct handling of rotations.
* Can be embedded as a child view controller of other controllers or deployed as the rootViewController.
* Plays nicely with any child view controllers or parent controllers.
* Can be deployed as a child of itself to create cascade-like, hierarchical interfaces.
* Seamless integration of pan gesture recognizer, behaving as smooth as silk.
* A category method on UIViewController, `revealViewController`, to get the parent `SWRevealViewController` of any child controller, similar to the UIViewController's property `navigationController`.
* Lightweight, clean, easy-to-read, self-documenting code that you will enjoy using in your projects.

## Examples

![Dynamic](https://raw.github.com/John-Lluch/SWRevealViewController/master/SWRevealViewController3.png)
![Dynamic](https://raw.github.com/John-Lluch/SWRevealViewController/master/SWRevealViewController.png)


## Requirements

* iOS 5.1 through iOS 7.0 or later.
* ARC memory management.

## Usage

`SWRevealViewController` attempts to provide an updated cocoaPods file and consistent tag versioning, but it is not actively updated on the cocoapods-specs repository.

The easier way to install it is by copying the following to your project:
* SWRevealViewController.h
* SWRevealViewController.m

* Initialize an instance of a SWRevealViewController passing in a "rear" and a "front" view controllers.
* Use the SWRevealViewController instance in your code as you would use any view controller.
* Deploy as the application window rootViewController, or as a child of other containment controllers.
* Add the panGestureRecognized provided by the SWRevealViewController to a suitable view of your "front" view controller, for example use the viewDidLoad method of your controller to add the gesture recognizer to a navigationBar.
* At any time, you can reveal, conceal the "rear" view or replace the "front" view controller, programmatically or based on user actions, with or without animations enabled

## Basic API Description

Initializing a SWRevealViewController:

    - (id)initWithRearViewController:(UIViewController *)rearViewController frontViewController:(UIViewController *)frontViewController;

Setting the right view controller:

	@property (strong, nonatomic) UIViewController *rightViewController;
	
Animated setting of the front view controller:

    - (void)setFrontViewController:(UIViewController *)frontViewController animated:(BOOL)animated;

Animating the position of the front view controller. Position can be: `FrontViewPositionLeftSideMostRemoved`, `FrontViewPositionLeftSideMost`, `FrontViewPositionLeftSide`, `FrontViewPositionLeft`, `FrontViewPositionRight`, `FrontViewPositionRightMost` or `FrontViewPositionRightMostRemoved`

	- (void)setFrontViewPosition:(FrontViewPosition)frontViewPosition animated:(BOOL)animated;
	
Obtaining a gesture recognizer to add to your front view controller:

	- (UIPanGestureRecognizer*)panGestureRecognizer;
	
Other methods are documented in the SWRevealViewController.h header file. 


## Release Notes

As of November 15, 2013 Release Notes are updated on the class main header file. Please see `SWRevealViewController.h`

## Special Mentions

A Xamarin Binding project for this controller is available for download at https://github.com/Vandborg/SWRevealViewController-XamarinBinding.
Thanks to Jesper Vandborg for having contributed to this.
	
## License

Copyright (c) 2013 Joan Lluch <joan.lluch@sweetwilliamsl.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is furnished
to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

Early code inspired on a similar class by Philip Kluz (Philip.Kluz@zuui.org)
