# Analogy gRPC Log Server

<p align="center">
    
[![Gitter](https://badges.gitter.im/Analogy-LogViewer/community.svg)](https://gitter.im/Analogy-LogViewer/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge) 
[![Build Status](https://dev.azure.com/Analogy-LogViewer/Analogy%20Log%20Viewer/_apis/build/status/Analogy-LogViewer.Analogy.LogViewer.gRPCLogServer?branchName=master)](https://dev.azure.com/Analogy-LogViewer/Analogy%20Log%20Viewer/_build/latest?definitionId=35&branchName=master) <a href="https://github.com/Analogy-LogViewer/Analogy.LogViewer.gRPCLogServer/issues">
    <img src="https://img.shields.io/github/issues/Analogy-LogViewer/Analogy.LogViewer.gRPCLogServer"  alt="Issues" />
</a>
![GitHub closed issues](https://img.shields.io/github/issues-closed-raw/Analogy-LogViewer/Analogy.LogViewer.gRPCLogServer)
<a href="https://github.com/Analogy-LogViewer/Analogy.LogViewer.gRPCLogServer/blob/master/LICENSE.md">
    <img src="https://img.shields.io/github/license/Analogy-LogViewer/Analogy.LogViewer.gRPCLogServer"  alt="License" />
</a>
</p>

gRPC Log Server (Windows Services) to receive and then forward messages to Analogy Log Viewer

Combined with  https://github.com/Analogy-LogViewer/Analogy.LogViewer.gRPC


## Usage
Once you have setup Analogy Log Server you can start sending messages to it:
Add Nuget package [Analogy.AspNetCore.LogProvider](Analogy.AspNetCore.LogProvider) and then add to the Configure method the following in te Startup.cs

```csharp

 public void Configure(IApplicationBuilder app, IWebHostEnvironment env, ILoggerFactory loggerFactory)
 {
     loggerFactory.AddAnalogyLogger(new AnalogyLoggerConfiguration
     {
         LogLevel = LogLevel.Trace,
         EventId = 0,
         AnalogyServerUrl = "http://localhost:6000"
      });
     }

```

