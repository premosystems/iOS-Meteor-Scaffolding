iOS-Meteor-Scaffolding
======================

A very opinionated command line tool for MVC scaffolding of iOS projects with a Meteor back end.

### Project

* An XCode/iOS and Meteor project are created with a specific directory structure.
* The XCode project has the concept of a 2 or 3 letter <XCode-Prefix> to be prepended to each class name.

### Command Line tool

* ios-meteor create:project \[ProjectName\] \[XCode-Prefix]]
* ios-meteor scaffold:model
* ios-meteor create:model
* ios-meteor create:view
* ios-meteor create:controller

### Folder structure

```
<Project-Name>-iOS/ 													# iOS Project Folder created by the command line tool
	Source/																# iOS Source Code
		Controller/														# MVC Controller logic, a "private" Cocoapod
			Classes/
				<Model-Object>/											# Controller classes for each model object are placed in a separate directory.
			<Project-Name>-Controller.podspec
		Model/															# MVC Model Logic, a "private" Cocoapod
			Classes/
				<Model-Object>/											# POCO classes for each model object are placed in a separate directory.
					<Model-Object>/	    								# The directory created for the model object by the command line tool when executed by the user. e.g. Widget
						<XCode-Prefix><Model-Object>.h					# The POCO Model Object
						<XCode-Prefix><Model-Object>.m
						<XCode-Prefix><Model-Object>+ModelAdditions.h	# A category addition for model convenience methods
						<XCode-Prefix><Model-Object>+ModelAdditions.m
			<Project-Name>-Model.podspec
		View/															# MVC View, the XCode app project
		Podfile
	provisioning/														# Apple provisioning assets, certificates, etc.
<Project-Name>-Meteor/ 													# Meteor Project Folder created by the command line tool
																		# Follows MatteOdem's awesome meteor-boilerplate

```

### Projects used

* [meteor-boilerplate](https://github.com/matteodem/meteor-boilerplate)
* [Xcodeproj](https://github.com/CocoaPods/Xcodeproj)
