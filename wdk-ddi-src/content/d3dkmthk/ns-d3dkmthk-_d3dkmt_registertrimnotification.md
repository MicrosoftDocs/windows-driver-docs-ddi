---
UID: NS:d3dkmthk._D3DKMT_REGISTERTRIMNOTIFICATION
title: "_D3DKMT_REGISTERTRIMNOTIFICATION"
author: windows-driver-content
description: D3DKMT_REGISTERTRIMNOTIFICATION is used with D3DKMTRegisterTrimNotification to register a callback for a kernel mode device for notifications from a graphics framework (such as OpenGL).
old-location: display\d3dkmt_registertrimnotification.htm
old-project: display
ms.assetid: CA5BC76B-539E-4FFF-8E02-C475D18588F6
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: D3DKMT_REGISTERTRIMNOTIFICATION, D3DKMT_REGISTERTRIMNOTIFICATION structure [Display Devices], _D3DKMT_REGISTERTRIMNOTIFICATION, d3dkmthk/D3DKMT_REGISTERTRIMNOTIFICATION, display.d3dkmt_registertrimnotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMT_REGISTERTRIMNOTIFICATION
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_REGISTERTRIMNOTIFICATION
---

# _D3DKMT_REGISTERTRIMNOTIFICATION structure


## -description


<b>D3DKMT_REGISTERTRIMNOTIFICATION</b> is used with <a href="https://msdn.microsoft.com/library/windows/hardware/dn906781">D3DKMTRegisterTrimNotification</a> to register a callback for a kernel mode device for notifications from a graphics framework (such as OpenGL).




## -struct-fields




### -field AdapterLuid

[in] Luid of the adapter which the device created.


### -field hDevice

[in] Device to trim the residency list for.


### -field Callback

[in] Pointer to the callback function.


### -field Context

[in] Caller-supplied context for callback.


### -field Handle

[out] Handle that will be used to unregister the callback with <a href="https://msdn.microsoft.com/library/windows/hardware/dn906787">D3DKMTUnregisterTrimNotification</a>.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906781">D3DKMTRegisterTrimNotification</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906787">D3DKMTUnregisterTrimNotification</a>
 

 

