---
UID: NF:d3dkmthk.D3DKMTRegisterTrimNotification
title: D3DKMTRegisterTrimNotification function
author: windows-driver-content
description: D3DKMTRegisterTrimNotification is used by a kernel mode video memory manager to register and implement a callback for each kernel mode device to receive notifications from a graphics framework (such as OpenGL).
old-location: display\d3dkmtregistertrimnotification.htm
old-project: display
ms.assetid: 4D35ED8F-2D1E-4C0B-8302-CE651D47AF10
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTRegisterTrimNotification
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTRegisterTrimNotification
req.alt-loc: GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTRegisterTrimNotification function



## -description
<b>D3DKMTRegisterTrimNotification</b> is used by a kernel mode video memory manager to register and implement a callback for each kernel mode device to receive notifications from a graphics framework (such as OpenGL).



## -syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTRegisterTrimNotification(
  _Inout_ D3DKMT_REGISTERTRIMNOTIFICATION *pData
);
````


## -parameters

### -param pData [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_registertrimnotification.md">D3DKMT_REGISTERTRIMNOTIFICATION</a> structure that describes the operation.


## -returns
Returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The operation was performed successfully.
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>
         Parameters were validated and determined to be incorrect.

 

This function might also return other <b>NTSTATUS</b> values.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_registertrimnotification.md">D3DKMT_REGISTERTRIMNOTIFICATION</a>
</dt>
<dt>
<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtunregistertrimnotification.md">D3DKMTUnregisterTrimNotification</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTRegisterTrimNotification function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

