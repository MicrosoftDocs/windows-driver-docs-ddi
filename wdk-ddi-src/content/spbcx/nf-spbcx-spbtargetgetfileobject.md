---
UID: NF:spbcx.SpbTargetGetFileObject
title: SpbTargetGetFileObject function
author: windows-driver-content
description: The SpbTargetGetFileObject method accepts, as an input parameter, an SPBTARGET handle to an open target device, and returns a WDFFILEOBJECT handle to this target.
old-location: spb\spbtargetgetfileobject.htm
old-project: SPB
ms.assetid: A89635EC-F5B8-4427-9AFD-9F71339595DF
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: spbcx/SpbTargetGetFileObject, SpbTargetGetFileObject, SPB.spbtargetgetfileobject, SpbTargetGetFileObject method [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: spbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	spbcxstubs.lib
-	spbcxstubs.dll
apiname:
-	SpbTargetGetFileObject
product: Windows
targetos: Windows
req.typenames: "*PSPB_REQUEST_TYPE, SPB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# SpbTargetGetFileObject function


## -description


The <b>SpbTargetGetFileObject</b> method accepts, as an input parameter, an SPBTARGET handle to an open target device, and returns a WDFFILEOBJECT handle to this target.


## -syntax


````
WDFFILEOBJECT SpbTargetGetFileObject(
  _In_ SPBTARGET Target
);
````


## -parameters




### -param Target [in]

An <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to a target device on the bus.


## -returns



<b>SpbTargetGetFileObject</b> returns a WDFFILEOBJECT handle to an open target device on the bus. The method returns NULL if the connection to the target was closed by an <a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a> event callback.




## -remarks



Your controller driver can call this method to obtain a WDFFILEOBJECT handle to an open target device on the bus. The SPB controller driver can then use this handle as an input parameter to WDF methods that require such a handle.

<b>SpbTargetGetFileObject</b> returns NULL only if the WDFFILEOBJECT handle to the target was closed but, before it closed, the SPB controller driver took an additional reference on the SBPTARGET object to extend its lifetime.

If the connection was closed and the SPB controller driver holds no references to the SPBTARGET object, the SBPTARGET handle is no longer valid. Passing an invalid handle to <b>SpbTargetGetFileObject</b> causes a bug check.

After <b>SpbTargetGetFileObject</b> returns a WDFFILEOBJECT handle, there is no guarantee that the target connection will remain open unless another object (for example, an active I/O request) holds a reference to the WDFFILEOBJECT object to prevent it from closing unexpectedly.  This method is most useful, and, therefore, most likely to be called, when the target connection is guaranteed to be open. Typically, such calls occur during <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> and <a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a> callbacks, and during the processing of I/O requests.




## -see-also

<a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a>



<a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [SPB\buses]:%20SpbTargetGetFileObject method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

