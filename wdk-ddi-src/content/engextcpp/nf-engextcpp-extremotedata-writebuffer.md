---
UID: NF:engextcpp.ExtRemoteData.WriteBuffer
title: ExtRemoteData::WriteBuffer method
author: windows-driver-content
description: The WriteBuffer method writes data to the target's memory. The data is located in the beginning of the region represented by the ExtRemoteData object. However, the size of the data can be different.
old-location: debugger\extremotedata_writebuffer.htm
old-project: debugger
ms.assetid: b50f0cf3-4cd5-4f9e-9749-49b1c9365a8f
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: ExtRemoteData, WriteBuffer method [Windows Debugging], ExtRemoteData::WriteBuffer, WriteBuffer, ExtRemoteData class [Windows Debugging], WriteBuffer method, EngExtCpp_Ref_0a08b058-ddc3-44e4-9d80-bb20d6e8f952.xml, debugger.extremotedata_writebuffer, WriteBuffer method [Windows Debugging], ExtRemoteData class
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
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
req.lib: engextcpp.hpp
req.dll: 
req.irql: 
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	COM
apilocation: 
-	engextcpp.hpp
apiname: 
-	ExtRemoteData.WriteBuffer
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::WriteBuffer method


## -description


The <b>WriteBuffer</b> method writes data to the target's memory.  The data is located in the beginning of the region represented by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object.  However, the size of the data can be different.


## -syntax


````
ULONG WriteBuffer(
  [in] PVOID Buffer,
  [in] ULONG Bytes,
  [in] bool  MustReadAll
);
````


## -parameters




### -param Buffer [in]

Specifies the data to write to the target.


### -param Bytes [in]

Specifies the number of bytes to write.  The <i>Buffer</i> buffer must be at least this size.


### -param MustWriteAll





#### - MustReadAll [in]

Specifies what happens if the debugger engine is unable to write all the data to the target.  If <i>MustReadAll</i> is <code>true</code> and the debugger engine is unable to write <i>Bytes</i> bytes to the target, an <b>ExtRemoteException</b> will be thrown.  If <i>MustReadAll</i> is <code>false</code>, no exception will be thrown if the engine is unable to write the requested number of bytes to the target.


## -returns


<b>WriteBuffer</b> returns the number of bytes written to the target from the <i>Buffer</i> buffer.  If <i>MustReadAll</i> is <code>true</code>, the value of <i>Bytes</i> will be returned (unless an exception is thrown).



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544088">ExtRemoteData::ReadBuffer</a>

<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.WriteBuffer method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

