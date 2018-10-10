api.ai: .NET Core Library
==============

[![Build Status](https://travis-ci.org/api-ai/apiai-dotnet-client.svg?branch=master)](https://travis-ci.org/api-ai/apiai-dotnet-client)
[![Nuget Version](https://img.shields.io/nuget/v/ApiAiSDK.svg)](https://www.nuget.org/packages/ApiAiSDK/)

The api.ai .NET Library makes it easy to integrate the [API.AI natural language processing API](http://api.ai) into your .NET application. API.AI allows using voice commands and integration with dialog scenarios defined for a particular agent in API.AI.

Library provides simple programming interface for making text and voice requests to the API.AI service. 

## Getting started

### Installation

You can be downloaded as sources from the [Releases](https://github.com/gosha20777/dialogflow-dotnetcore-client/releases) page.

### Usage

Assumed you already have API.AI account and have at least one agent configured. If no, please see [documentation](http://api.ai/docs/index.html) on the API.AI website.

First, add following usages to your module:
```csharp
using ApiAiSDK;
using ApiAiSDK.Model;
```

Then add `ApiAi` field to your class:
```csharp
private ApiAi apiAi;
```

Now you need to initialize `ApiAi` object with appropriate access keys and language.
```csharp
var config = new AIConfiguration("YOUR_CLIENT_ACCESS_TOKEN", SupportedLanguage.English);
apiAi = new ApiAi(config);
```

Done! Now you can easily do requests to the API.AI service 
* using `TextRequest` method for simple text requests
    ```csharp
    var response = apiAi.TextRequest("hello");
    ```

* using `VoiceRequest` method for voice binary data in PCM (16000Hz, Mono, Signed 16 bit) format
    ```csharp
    var response = apiAi.VoiceRequest(voiceStream);
    ```

Also see [unit tests](https://github.com/api-ai/api-ai-net/blob/master/ApiAiSDK.Tests/ApiAiTest.cs) for more examples.

## Open Source Project Credits

* JSON parsing implemented using [Json.NET](http://www.newtonsoft.com/json).

