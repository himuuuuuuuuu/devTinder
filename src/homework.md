# Create a repository
# Initialize the repository
# node_modules, package.json, package-lock.json
# Install express
# Create a Server
# Listen  to port 7777
# Write request handlers for /test, /hello
# Install nodemon and update scripts inside package.json
# What are dependencies.
# What is the use of "-g" while npm install
# Difference between tilde ( ~ ) and caret ( ^ ) in package.json.
. In package.json, the tilde (~) and caret (^) symbols are used to specify the version range for dependencies, controlling how updates are handled when you run npm install or yarn install. Tilde allows only the patch version upgrades avoiding the minor updates while caret allows updates to patch as well as minor versions.

. When we open our package.json file and search for the dependency property and in there we find the packages that are listed as a nested object of the dependency property package-name:package-version. Now look at the package version, we find some numbers separated by three dots. 

NPM versions follow a three-number format, separated by dots. The leftmost number signifies the major release, the second one represents the minor release, and the third number denotes the patch release of the package.

# Syntax: The syntax of the npm version looks like the following.

// package-name:  Major.Minor.Patch

"express": "~4.16.3" // tilde for patch updates
"express": "^4.16.3" //  caret for flexible updates

# Tilde (~) notation
The tilde (~) notation is employed to match the latest patch version while freezing the major and minor versions. This notation is useful for automatically accepting bug fixes, considering that patch updates primarily address bugs.

Example: The ~1.2.0 will update all the future patch updates. We have to write just ~1.2.0 and all the next patch update dependencies. For example, 1.2.1, 1.2.2, 1.2.5……………1.2.x.

. Patch updates are very small security changes in a package that is why the ~version is approximately equivalent to the version.

# Caret (^) notation
It automatically updates both minor and patch updates.

Example: The ^1.2.4 will update all the future Minor and patch updates, for example, ^1.2.4 will automatically change the dependency to 1.x.x if any update occurs. 

# Difference between tilde (~) and caret (^) in package.json
# Tilde (~) notation:
.Used for Approximately equivalent to version.
.It will update you to all future patch versions, without incrementing the minor version. ~1.2.3 will use releases from 1.2.3 to <1.3.
.It gives you bug fix releases.
.It will update in decimals.
.Not a default notation used by NPM.
.Example: ~1.0.2


# Caret (^) notation:
.Used for Compatible with version.
.It will update you to all future minor/patch versions, without incrementing the major version. ^2.3.4 will use releases from 2.3.4 to <3.0.0
.It gives you backwards-compatible new functionality as well.
.It will update to its latest version in numbers.
.Used by NPM as default notation.
.Example: ^1.0.2

#  package.json and package-lock.json files
. In Node, package.json file contains the list of dependencies and scripts in a project while the package.lock.json specifies their respective versions to ensure consistent installations in different environments.

# Difference between package.json and package-lock.json
# package.json
. It contains basic information about the project.
. It is mandatory for every project.
. It records important metadata about the project.
. It contains information such as name, description, author, script, and dependencies.

# package-lock.json
. It describes the exact tree that was generated to allow subsequent installs to have the identical tree.
. It is automatically generated for those operations where npm modifies either node_modules tree or package.json.
. It allows future devs to install the same dependencies in the project.
. It contains the name, dependencies, and locked version of the project. 

# Understanding Dependencies in Node.js Projects:
When working on a Node.js project, managing dependencies is a crucial aspect that ensures your project runs smoothly. Dependencies are the libraries or packages your project needs to function. There are two main types of dependencies you should be aware of: devDependencies and normal dependencies.

Types of Dependencies:
.These are the packages required only during the development phase. They are not needed in the production environment. For example, tools like parcel, webpack, or babel, which help in building or bundling your project, are usually listed as devDependencies.

Here's an example of how to define a devDependency in your package.json file:
"devDependencies": {
  "parcel": "^2.8.3"
}

.Normal Dependencies
These are the packages that your project needs in both development and production environments. Examples include frameworks like React, libraries for making HTTP requests, or any other code that your application relies on to run.

# package.json and package-lock.json
Both package.json and package-lock.json are essential for managing dependencies in a Node.js project, but they serve different purposes:

. package.json: This file lists the dependencies your project needs and can include version ranges (^ or ~).

. package-lock.json: This file locks down the exact versions of each dependency, ensuring that every time you or someone else installs the project, the same versions are used.

# Transitive Dependencies
Dependencies can have their own dependencies, creating a chain known as transitive dependencies. For example, Parcel might depend on other packages, and those packages might depend on even more packages. This chain is automatically managed for you, ensuring that all necessary packages are installed.

# What is the use of "-g" while npm install
The -g flag in npm install stands for "global." When you use npm install -g, it installs the package globally on your system, meaning the package will be available across all projects, not just the one in the current directory.

.Without -g: When you run npm install without -g, npm installs the package in the node_modules folder of your current project. This is called a local installation, and the package will only be available for use in that project.

.With -g: When you use npm install -g, the package gets installed globally, making it available from anywhere on your system.

Use Cases for Global Installation:
.Packages that are intended to be used as command-line tools (e.g., npm, gulp, eslint, nodemon).
npm install -g nodemon

.Packages that you want to be available system-wide, irrespective of the specific project you're working on.
npm install -g eslint
