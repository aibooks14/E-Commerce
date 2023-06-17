# E-Commerce
echo off
set fileDir=$dir                             // set file directory variable
set fileDir=%fileDir:"=%                     // remove quotes from directory path
javac -d bin -cp bin %fileDir%*.java         // compile all Java files in file directory
set class=%fileDir%$fileNameWithoutExt       // set fully qualified class name variable
set class=%class:$workspaceRoot\\src\\=%     // convert to path relative to sourcepath 
set class=%class:\=.%                        // switch out slashes for periods
java -cp bin %class%                         // launch the Java file
echo on
