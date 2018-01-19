---
UID: NF:d3dkmthk.D3DKMTEnumAdapters
title: D3DKMTEnumAdapters function
author: windows-driver-content
description: Enumerates all graphics adapters on the system.
old-location: display\d3dkmtenumadapters.htm
old-project: display
ms.assetid: 07c0aeac-0f82-492a-aa98-0ba5a962b9cf
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTEnumAdapters
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTEnumAdapters
req.alt-loc: Gdi32.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.lib
req.dll: Gdi32.dll
req.irql: 
req.typenames: D3DKMT_DRIVERVERSION
---

# D3DKMTEnumAdapters function



## -description
Enumerates all graphics adapters on the system.



## -syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTEnumAdapters(
  _Inout_ const D3DKMT_ENUMADAPTERS *pEnumAdapters
);
````


## -parameters

### -param pEnumAdapters [in, out]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_enumadapters.md">D3DKMT_ENUMADAPTERS</a> structure that lists all graphics adapters and their characteristics.


## -returns
Returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The enumeration was successful.
<dl>
<dt><b>STATUS_INVALID_PARAMETER </b></dt>
</dl>The  <i>pEnumAdapters</i> parameter was validated and determined to be incorrect.


 

This function might also return other NTSTATUS values.


## -remarks
The operating system enumerates graphics adapters in the same sequence as their corresponding physical devices.


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_enumadapters.md">D3DKMT_ENUMADAPTERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTEnumAdapters function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

