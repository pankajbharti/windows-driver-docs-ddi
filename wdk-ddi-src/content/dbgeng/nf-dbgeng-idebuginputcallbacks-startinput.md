---
UID: NF:dbgeng.IDebugInputCallbacks.StartInput
title: IDebugInputCallbacks::StartInput method
author: windows-driver-content
description: The StartInput callback method is called by the engine to indicate that it is waiting for a line of input.
old-location: debugger\idebuginputcallbacks_startinput.htm
old-project: debugger
ms.assetid: 4ac3764e-6482-49de-aac8-3b540561d201
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: StartInput method [Windows Debugging], StartInput, debugger.idebuginputcallbacks_startinput, dbgeng/IDebugInputCallbacks::StartInput, IDebugInputCallbacks, IDebugInputCallbacks::StartInput, IDebugInputCallbacks interface [Windows Debugging], StartInput method, ComCallbacks_155d62a2-08b2-4caf-80d6-80fab139e77b.xml, StartInput method [Windows Debugging], IDebugInputCallbacks interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	dbgeng.h
apiname: 
-	IDebugInputCallbacks.StartInput
product: Windows
targetos: Windows
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugInputCallbacks::StartInput method


## -description


The <b>StartInput</b> callback method is called by the engine to indicate that it is waiting for a line of input.


## -syntax


````
HRESULT StartInput(
  [in] ULONG BufferSize
);
````


## -parameters




### -param BufferSize [in]

Specifies the number of characters requested.  Any input longer than this size will be truncated.


## -returns


The return value is ignored by the engine unless it indicates a remote procedure call error; in this case the client, with which this <b>IDebugEventCallbacks</b> object is registered, is disabled.



## -remarks


This method indicates that the engine is waiting for a line of input from any client.  This can occur if, for example, the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550962">Input</a> method was called on a client.

After calling this method, the engine waits until it receives some input.  When it does receive input, it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff550791">IDebugInputCallbacks::EndInput</a> to inform all the <b>IDebugInputCallbacks</b> objects that are registered with clients that it is no longer waiting for input.

The <b>IDebugInputCallbacks</b> object can provide the engine with a line of input by calling either the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554600">ReturnInput</a> or <b>ReturnInputWide</b> methods.

For more information about debugger engine input, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.


