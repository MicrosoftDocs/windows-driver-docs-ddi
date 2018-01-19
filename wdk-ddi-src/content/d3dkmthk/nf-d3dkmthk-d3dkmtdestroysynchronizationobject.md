---
UID: NF:d3dkmthk.D3DKMTDestroySynchronizationObject
title: D3DKMTDestroySynchronizationObject function
author: windows-driver-content
description: The D3DKMTDestroySynchronizationObject function destroys a kernel-mode synchronization object.
old-location: display\d3dkmtdestroysynchronizationobject.htm
old-project: display
ms.assetid: 38e77d21-a386-4de8-8d1c-db48434828c6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DKMTDestroySynchronizationObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTDestroySynchronizationObject
req.alt-loc: Gdi32.dll,API-MS-Win-dx-d3dkmt-l1-1-0.dll,API-MS-Win-dx-d3dkmt-l1-1-1.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
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

# D3DKMTDestroySynchronizationObject function



## -description
The <b>D3DKMTDestroySynchronizationObject</b> function destroys a kernel-mode synchronization object.



## -syntax

````
NTSTATUS D3DKMTDestroySynchronizationObject(
  _In_ const D3DKMT_DESTROYSYNCHRONIZATIONOBJECT *pData
);
````


## -parameters

### -param pData [in]

A pointer to a <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroysynchronizationobject.md">D3DKMT_DESTROYSYNCHRONIZATIONOBJECT</a> structure that contains the handle to the synchronization object to destroy.


## -returns
<b>D3DKMTDestroySynchronizationObject</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The kernel-mode overlay object was successfully destroyed.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other <b>NTSTATUS</b> values.




## -remarks


## -see-also
<dl>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_destroysynchronizationobject.md">D3DKMT_DESTROYSYNCHRONIZATIONOBJECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTDestroySynchronizationObject function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

