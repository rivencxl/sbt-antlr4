# sbt-antlr4

This plugin provides an ability to run antlr4 when compiling in sbt 0.13.

## How to use

Put your .g4 files in `src/main/antlr4` directory and put Antlr4Plugin.scala in `project/`:

Then, add `antlr4Settings` to your `build.sbt` file.

    antlr4Settings

## Settings

`-package` option can be given by the following setting:

    antlr4PackageName in Antlr4 := Some("com.simplytyped")

You can also adjust `-listener`, `-no-listener`, `-visitor`, `-no-visitor` options:

    antlr4GenListener in Antlr4 := true // default: true

    antlr4GenVisitor in Antlr4 := false // default: false
Set output directory for generated java classes (eg parser):


    default directory: projectpath/target/resolution-cache/scala_{ver}/src_managed/main


    antlr4OutputDir in Antlr4 := new File("projectpath/where/You/want/")

And if You want put it to projectpath/src/main/java:

    antlr4OutputDir in Antlr4 := (javaSource in Compile).value 
 
## License

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
