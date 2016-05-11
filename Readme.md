# SSIS Build

### Overview 
This is a customised version of the SSIS MSBuild task taken the from 
[Microsoft SQL Server Community Samples: Integration Services project](https://sqlsrvintegrationsrv.codeplex.com/) on Codeplex. The code on which this customised version is based can be found [here](https://sqlsrvintegrationsrv.codeplex.com/SourceControl/latest#main/SSISMSBuild/Project/DeploymentFileCompilerTask.cs)

The Original SSIS MSBuild task extends MSBuild's capabilities allowing SSIS solutions (*.dtproj) to be built using MSSbuild without the need for Visual Studio. This is useful for build automation scenarios where a build server is used as part of a continuous integration process.  For more information on using the task see the blog post [Building SSIS 2012 using MSBuild – A Journey to DB deployment automation](https://speaksql.wordpress.com/2013/06/07/a-journey-to-db-deployment-automaton-ssis-build-using-msbuild/) which also an example msbuild *.proj file to get you started. Before you can use the task you need to compile the DLL and Simon D'Morias has a great article [here](http://www.sqlstash.com/2015/06/14/building-the-ssis-build-component/) on how to build the custom task. 


### Customisation

This version of the custom task adds the ability to include other files in the build output in addition to the ispac file. Think of it as a SSIS Project version of the "_Copy to Output Directory_" property that is available for files in other types of Visual Studio projects. This might be useful in a number of scenarios. For example, consider a SSIS Project that made use of a third party DLL in a custom script task. The DLL(s) could be added as _Misc_ items to the SSIS Project and when the project was built they would be included in the build output folder along with the ispac file. Similarly, in a SSIS project that was used to load a set of reference data, the files containing the data could be included as _Misc_ items in the SSIS Project and they would be automatically included with the build output.

### Building and using the custom task

TODO
