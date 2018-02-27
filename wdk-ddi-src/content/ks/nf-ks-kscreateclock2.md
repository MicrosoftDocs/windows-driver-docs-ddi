---
UID: NF:ks.KsCreateClock2
title: KsCreateClock2 function
author: windows-driver-content
description: Creates a handle to a clock instance. Call this function after the Component Object Model (COM) is initialized.
old-location: stream\kscreateclock2.htm
old-project: stream
ms.assetid: b70d4a57-c687-40b8-bbf2-4a0a2fbf4863
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: KsCreateClock2, KsCreateClock2 function [Streaming Media Devices], ks/KsCreateClock2, stream.kscreateclock2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ks.h
apiname:
-	KsCreateClock2
product: Windows
targetos: Windows
req.typenames: 
---

# KsCreateClock2 function


## -description


Creates a handle to a clock instance. Call this function after the Component Object Model (COM) is initialized.

Supported starting in Windows 8.


## -syntax


````
KSDDKAPI HRESULT NTAPI KsCreateClock2(
  _In_  HANDLE          ConnectionHandle,
  _In_  PKSCLOCK_CREATE ClockCreate,
  _Out_ PHANDLE         ClockHandle
);
````


## -parameters




### -param ConnectionHandle [in]

Specifies the handle to the connection on which to create the clock.


### -param ClockCreate [in]

Specifies clock create parameters. This currently consists of a flag that must be set to zero.


### -param ClockHandle [out]

Specifies the new clock handle.


## -returns



Returns <b>NOERROR</b> if successful; otherwise, returns an error code.




## -remarks



This is a new version of the <a href="..\ks\nf-ks-kscreateclock.md">KsCreateClock</a> function and uses the device broker to create the handle to the kernel streaming object. In addition, the COM <a href="https://msdn.microsoft.com/0f171cf4-87b9-43a6-97f2-80ed344fe376">CoInitialize</a> function must be called before this function is called.




## -see-also

<a href="..\ks\nf-ks-kscreateclock.md">KsCreateClock</a>



<a href="https://msdn.microsoft.com/0f171cf4-87b9-43a6-97f2-80ed344fe376">CoInitialize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCreateClock2 function%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

