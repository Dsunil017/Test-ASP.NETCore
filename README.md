# Test-ASP.NETCore
ASP.NET Core stuff
when I update asp.net core 2.1.I got following error
fail: Microsoft.AspNetCore.Authentication.JwtBearer.JwtBearerHandler[3]
 Exception occurred while processing message.
System.InvalidOperationException: IDX20803: Unable to obtain configuration from: 'https://app01.cloudapp.net:9003/Test/.well-known/openid-configuration''. ---> System.IO.IOException: IDX20804: Unable to retrieve document from: 'https://app01.cloudapp.net:9003/Test/.well-known/openid-configuration'. ---> System.Net.Http.HttpRequestException: The SSL connection could not be established, see inner exception. ---> System.Security.Authentication.AuthenticationException: The remote certificate is invalid according to the validation procedure.
 at System.Net.Security.SslState.StartSendAuthResetSignal(ProtocolToken message, AsyncProtocolRequest asyncRequest, ExceptionDispatchInfo exception)
 at System.Net.Security.SslState.CheckCompletionBeforeNextReceive(ProtocolToken message, AsyncProtocolRequest asyncRequest)
 at System.Net.Security.SslState.StartSendBlob(Byte[] incoming, Int32 count, AsyncProtocolRequest asyncRequest)
 at System.Net.Security.SslState.ProcessReceivedBlob(Byte[] buffer, Int32 count, AsyncProtocolRequest asyncRequest)
 at System.Net.Security.SslState.StartReadFrame(Byte[] buffer, Int32 readBytes, AsyncProtocolRequest asyncRequest)
 at System.Net.Security.SslState.StartReceiveBlob(Byte[] buffer, AsyncProtocolRequest asyncRequest)
 at System.Net.Security.SslState.CheckCompletionBeforeNextReceive(ProtocolToken message, AsyncProtocolRequest asyncRequest)
 at System.Net.Security.SslState.StartSendBlob(Byte[] incoming, Int32 count, AsyncProtocolRequest asyncRequest)
 at System.Net.Security.SslState.ProcessReceivedBlob(Byte[] buffer, Int32 count, AsyncProtocolRequest asyncRequest)
 at System.Net.Security.SslState.StartReadFrame(Byte[] buffer, Int32 readBytes, AsyncProtocolRequest asyncRequest)
 at System.Net.Security.SslState.PartialFrameCallback(AsyncProtocolRequest asyncRequest)
--- End of stack trace from previous location where exception was thrown ---
 at System.Net.Security.SslState.ThrowIfExceptional()
 at System.Net.Security.SslState.InternalEndProcessAuthentication(LazyAsyncResult lazyResult)
 at System.Net.Security.SslState.EndProcessAuthentication(IAsyncResult result)
 at System.Net.Security.SslStream.EndAuthenticateAsClient(IAsyncResult asyncResult)
 at System.Net.Security.SslStream.<>c.<AuthenticateAsClientAsync>b__47_1(IAsyncResult iar)
 at System.Threading.Tasks.TaskFactory`1.FromAsyncCoreLogic(IAsyncResult iar, Func`2 endFunction, Action`1 endAction, Task`1 promise, Boolean requiresSynchronization)
--- End of stack trace from previous location where exception was thrown ---
 at System.Net.Http.ConnectHelper.EstablishSslConnectionAsyncCore(Stream stream, SslClientAuthenticationOptions sslOptions, CancellationToken cancellationToken)
 --- End of inner exception stack trace ---
 at System.Net.Http.ConnectHelper.EstablishSslConnectionAsyncCore(Stream stream, SslClientAuthenticationOptions sslOptions, CancellationToken cancellationToken)
 at System.Threading.Tasks.ValueTask`1.get_Result()
 at System.Net.Http.HttpConnectionPool.CreateConnectionAsync(HttpRequestMessage request, CancellationToken cancellationToken)
 at System.Threading.Tasks.ValueTask`1.get_Result()
 at System.Net.Http.HttpConnectionPool.WaitForCreatedConnectionAsync(ValueTask`1 creationTask)
 at System.Threading.Tasks.ValueTask`1.get_Result()
 at System.Net.Http.HttpConnectionPool.SendWithRetryAsync(HttpRequestMessage request, Boolean doRequestAuth, CancellationToken cancellationToken)
 at System.Net.Http.RedirectHandler.SendAsync(HttpRequestMessage request, CancellationToken cancellationToken)
 at System.Net.Http.HttpClient.FinishSendAsyncBuffered(Task`1 sendTask, HttpRequestMessage request, CancellationTokenSource cts, Boolean disposeCts)
 at Microsoft.IdentityModel.Protocols.HttpDocumentRetriever.GetDocumentAsync(String address, CancellationToken cancel)
 --- End of inner exception stack trace ---
 at Microsoft.IdentityModel.Protocols.HttpDocumentRetriever.GetDocumentAsync(String address, CancellationToken cancel)
 at Microsoft.IdentityModel.Protocols.OpenIdConnect.OpenIdConnectConfigurationRetriever.GetAsync(String address, IDocumentRetriever retriever, CancellationToken cancel)
 at Microsoft.IdentityModel.Protocols.ConfigurationManager`1.GetConfigurationAsync(CancellationToken cancel)
 --- End of inner exception stack trace ---
 at Microsoft.IdentityModel.Protocols.ConfigurationManager`1.GetConfigurationAsync(CancellationToken cancel)
 at Microsoft.AspNetCore.Authentication.JwtBearer.JwtBearerHandler.HandleAuthenticateAsync()
