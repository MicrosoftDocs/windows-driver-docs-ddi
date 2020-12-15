---
UID: NF:spbcx.SpbTargetGetFileObject
title: SpbTargetGetFileObject function (spbcx.h)
description: The SpbTargetGetFileObject method accepts, as an input parameter, an SPBTARGET handle to an open target device, and returns a WDFFILEOBJECT handle to this target.
old-location: spb\spbtargetgetfileobject.htm
tech.root: SPB
ms.date: 04/30/2018
keywords: ["SpbTargetGetFileObject function"]
ms.keywords: SPB.spbtargetgetfileobject, SpbTargetGetFileObject, SpbTargetGetFileObject method [Buses], spbcx/SpbTargetGetFileObject
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
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - SpbTargetGetFileObject
 - spbcx/SpbTargetGetFileObject
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - spbcxstubs.lib
 - spbcxstubs.dll
api_name:
 - SpbTargetGetFileObject
---

# SpbTargetGetFileObject function


## -description

The <b>SpbTargetGetFileObject</b> method accepts, as an input parameter, an SPBTARGET handle to an open target device, and returns a WDFFILEOBJECT handle to this target.

## -parameters

### -param Target 

[in]
An <a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to a target device on the bus.

## -returns

<b>SpbTargetGetFileObject</b> returns a WDFFILEOBJECT handle to an open target device on the bus. The method returns NULL if the connection to the target was closed by an <a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_disconnect">EvtSpbTargetDisconnect</a> event callback.

## -remarks

Your controller driver can call this method to obtain a WDFFILEOBJECT handle to an open target device on the bus. The SPB controller driver can then use this handle as an input parameter to WDF methods that require such a handle.

<b>SpbTargetGetFileObject</b> returns NULL only if the WDFFILEOBJECT handle to the target was closed but, before it closed, the SPB controller driver took an additional reference on the SBPTARGET object to extend its lifetime.

If the connection was closed and the SPB controller driver holds no references to the SPBTARGET object, the SBPTARGET handle is no longer valid. Passing an invalid handle to <b>SpbTargetGetFileObject</b> causes a bug check.

After <b>SpbTargetGetFileObject</b> returns a WDFFILEOBJECT handle, there is no guarantee that the target connection will remain open unless another object (for example, an active I/O request) holds a reference to the WDFFILEOBJECT object to prevent it from closing unexpectedly.  This method is most useful, and, therefore, most likely to be called, when the target connection is guaranteed to be open. Typically, such calls occur during <a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a> and <a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_disconnect">EvtSpbTargetDisconnect</a> callbacks, and during the processing of I/O requests.

## -see-also

<a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_connect">EvtSpbTargetConnect</a>



<a href="/windows-hardware/drivers/ddi/spbcx/nc-spbcx-evt_spb_target_disconnect">EvtSpbTargetDisconnect</a>



<a href="/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>
