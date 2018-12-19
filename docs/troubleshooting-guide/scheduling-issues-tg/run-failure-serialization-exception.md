---
title: Run Failure With Serialization Exception
page_title: Run failure with SerializationException
description: "Test Studio is an innovative and easy-to-use automated web, WPF and load testing solution. Test Studio tests support essential technologies like ASP.NET AJAX, Silverlight, PHP and MVC. HTML5, Testing framework, functional testing, performance testing, load testing, exploratory testing, manual testing."
position: 1
---
# Run failure with SerializationException

In environments where Runtime version is installed only, there are "SerializationException" errors during start of remote run or after it ends and tries to report result to Storage Server:

<pre>
System.Runtime.Serialization.SerializationException was unhandled
  Message=Type 'System.ServiceModel.Channels.ReceivedFault' in Assembly 'System.ServiceModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089' is not marked as serializable.
  Source=mscorlib
  StackTrace:
       at System.Runtime.Serialization.FormatterServices.InternalGetSerializableMembers(RuntimeType type)
       at System.Runtime.Serialization.FormatterServices.GetSerializableMembers(Type type, StreamingContext context)
       at System.Runtime.Serialization.Formatters.Binary.WriteObjectInfo.InitMemberInfo()
       at System.Runtime.Serialization.Formatters.Binary.WriteObjectInfo.InitSerialize(Object obj, ISurrogateSelector surrogateSelector, StreamingContext context, SerObjectInfoInit serObjectInfoInit, IFormatterConverter converter, ObjectWriter objectWriter, SerializationBinder binder)
       at System.Runtime.Serialization.Formatters.Binary.ObjectWriter.Write(WriteObjectInfo objectInfo, NameInfo memberNameInfo, NameInfo typeNameInfo)
       at System.Runtime.Serialization.Formatters.Binary.ObjectWriter.Serialize(Object graph, Header[] inHeaders, __BinaryWriter serWriter, Boolean fCheck)
       at System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize(Stream serializationStream, Object graph, Header[] headers, Boolean fCheck)
       at ArtOfTest.WebAii.Messaging.Process.PipeCommand.ToBinary()
       at ArtOfTest.WebAii.Messaging.Process.PipeCommunication.WriteCommandToPipe(PipeCommand command, PipeStream pipe, Boolean waitForDrain)
       at ArtOfTest.WebAii.Design.Execution.RemoteRunner.OnTestComplete(ExecutionReturnValues retValues, Boolean displayResults)
       at ArtOfTest.WebAii.Design.Execution.ExecutionEngine.TestCompleted(IAsyncResult result)
       at System.Runtime.Remoting.Messaging.AsyncResult.SyncProcessMessage(IMessage msg)
       at System.Runtime.Remoting.Messaging.StackBuilderSink.AsyncProcessMessage(IMessage msg, IMessageSink replySink)
       at System.Runtime.Remoting.Proxies.AgileAsyncWorkerItem.DoAsyncCall()
       at System.Runtime.Remoting.Proxies.AgileAsyncWorkerItem.ThreadPoolCallBack(Object o)
       at System.Threading.QueueUserWorkItemCallback.WaitCallback_Context(Object state)
       at System.Threading.ExecutionContext.Run(ExecutionContext executionContext, ContextCallback callback, Object state, Boolean ignoreSyncCtx)
       at System.Threading.QueueUserWorkItemCallback.System.Threading.IThreadPoolWorkItem.ExecuteWorkItem()
       at System.Threading.ThreadPoolWorkQueue.Dispatch()
       at System.Threading._ThreadPoolWaitCallback.PerformWaitCallback()
</pre>

## SOLUTION

Installing <a href="http://www.microsoft.com/en-us/download/details.aspx?id=40779" target="_blank">.NET 4.5.1</a> will fix the issue.
