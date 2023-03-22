Q. NPM for beginner level.
=> NPM(short for node package manager) is a package manager for node.js. It is used to install and manage third-party lib., also known as 'packages', which can be used in Node.js projects.
	-When anyone starts a new Node.js project, they typically create a 'package.json' file, which contains information about your project and the packages that it depends on. This file is used by NPM to manage dependencies and install packages.
	- Key concepts for NPM only for beginners:
		1. Installing packages: You can install packages using the `npm install` command followed by the name of the package. For ex., to install the popular `express` package, you would run `npm install express`. By default, NPM installs packages in a `node_modules` directory in your project.
		2. Managing dependencies: NPM manages dependencies for your project through your `package.json` file. When you install a package, NPM adds it to the `dependencies` section of your `package.json`.
			-You can also install packages as `devDependencies` if they are only needed for development(ex., testing frameworks). To remove a package, you can use the `npm uninstall` command followed by the name of the package.
		3. Running scripts: NPM allows you to define scripts in your `package.json` file, which you can run using the `npm run` command followed by the script name. For example, you might define a script called to `start` that starts your server, and then run it using `npm run start`.
		4. Updating packages: You can check for outdated packages using the `npm outdated` command, and update them using the `npm update` command. To update a specific package, you can use `npm update <package-name>`. Be careful when updating packages, as they may introduce breaking changes that could affect your project.
		5. Publishing packages: If you create a package that you want to share with others, you can publish it to the NPM registry using the `npm publish` command. You'll need to create an account on the NPM website and follow their guidelines for publishing packages.

Q. What is a license? Why they are used in online projects? what types of licenses there are available? why you should include one in your projects?
=>Licenses are legal agreements that define how a particular software or project can be used, modified, and distributed. When you publish a project on Github or any other online platform, you are making it available for others to use and contribute to. By adding a license to your project, you are clarifying the terms under which others can use your work.
	-The MIT License is a popular open-source license that allows others to use, modify, and distribute your project for any purpose, including commercial purposes. It is often referred to as a permissive license because it places very few restrictions on how others can use your code. The license requires that anyone who uses or distributes your code must include the original copyright notice and disclaimer.








1. challenge : added "author" : "<my_name>" // added my name in the place of <my_name>, Devanshukoli
	-> It gave importance that which author this file belongs to and I have done that in the package.json file. Which is the center of all the node.js projects similar to <head> tag in HTML.
NOTE: Remember to use double quotes for fields("") and commas(,) to separate fields.

2. challenge: this challenge contains adding the `description` field to the package.json file.
In details section of the module says that when any user/devs come to your projects then they could decide whether to install your package or not.
so the task was: to add "description" " "A project that does something awesome", in the package.json file.

3. challenge: add 'keyword' in the package.json file. {"keyword": ["descriptive", "related", "words" ]}.

4. challenge: Add a License to Your package.json => it is so much important cuz its a legal license to your project/soft.  

5. challenge: Add a Version to Your package.json

6. challenge: Expand Your Project with External Packages from npm => One of the biggest reasons to use a package manager, is its powerful dependency management. Instead of manually having to make sure that you get all dependencies whenever you set up a project on a new computer, npm automatically installs everything for you.

7. challenge: Manage npm Dependencies By Understanding Semantic Versioning => Versions of the npm packages in the dependencies section of your package.json file follow what’s called Semantic Versioning (SemVer), an industry standard for software versioning aiming to make it easier to manage dependencies. Libraries, frameworks or other tools published on npm should use SemVer in order to clearly communicate what kind of changes projects can expect if they update.
	- Knowing SemVer can be useful when you develop software that uses external dependencies (which you almost always do). One day, your understanding of these numbers will save you from accidentally introducing breaking changes to your project without understanding why things that worked yesterday suddenly don’t work today. This is how Semantic Versioning works according to the official website:
		-"package": "MAJOR.MINOR.PATCH"	
	- The MAJOR version should increment when you make incompatible API changes. The MINOR version should increment when you add functionality in a backward-compatible manner. The PATCH version should increment when you make backward-compatible bug fixes. This means that PATCHes are bug fixes and MINORs add new features but neither of them breaks what worked before. Finally, MAJORs add changes that won’t work with earlier versions.

8. challenge: Use the Tilde-Character to Always Use the Latest Patch Version of a Dependency => In the last challenge, you told npm to only include a specific version of a package. That’s a useful way to freeze your dependencies if you need to make sure that different parts of your project stay compatible with each other. But in most use cases, you don’t want to miss bug fixes since they often include important security patches and (hopefully) don’t break things in doing so.
	- To allow an npm dependency to update to the latest PATCH version, you can prefix the dependency’s version with the tilde (~) character. Here's an example of how to allow updates to any `1.3.x` version.
		ex: "package": "~1.3.8"

9. challenge: Use the Caret-Character to Use the Latest Minor Version of a Dependency  =>
Similar to how the tilde we learned about in the last challenge allows npm to install the latest PATCH for a dependency, the caret (^) allows npm to install future updates as well. The difference is that the caret will allow both MINOR updates and PATCHes.
	- Your current version of @freecodecamp/example should be ~1.2.13 which allows npm to install to the latest 1.2.x version. If you were to use the caret (^) as a version prefix instead, npm would be allowed to update to any 1.x.x version.
		ex: "package": "^1.3.8" (This would allow updates to any `1.x.x` version of the package.)
NOTE: The version numbers themselves should not be changed.

10. challenge: Remove a Package from Your Dependencies => You have now tested a few ways you can manage dependencies of your project by using the package.json's dependencies section. You have also included external packages by adding them to the file and even told npm what types of versions you want, by using special characters such as the tilde or the caret.
	-But what if you want to remove an external package that you no longer need? You might already have guessed it, just remove the corresponding key-value pair for that package from your dependencies.
	-This same method applies to removing other fields in your package.json as well.
Note: Make sure you have the right amount of commas after removing it.























