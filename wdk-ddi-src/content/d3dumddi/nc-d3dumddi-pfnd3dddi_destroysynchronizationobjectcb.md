---
UID: NC:d3dumddi.PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB
title: PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB
author: windows-driver-content
description: The pfnDestroySynchronizationObjectCb function destroys the synchronization object that was created through a call to the pfnCreateSynchronizationObjectCb function.
old-location: display\pfndestroysynchronizationobjectcb.htm
old-project: display
ms.assetid: 7ba549a2-f165-4b5e-8cf4-ab707222532c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfndestroysynchronizationobjectcb, pfnDestroySynchronizationObjectCb callback function [Display Devices], pfnDestroySynchronizationObjectCb, PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB, PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB, d3dumddi/pfnDestroySynchronizationObjectCb, D3Druntime_Functions_a2b3f092-097e-4eb1-b38d-8f68e5edbcca.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	pfnDestroySynchronizationObjectCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB callback


## -description


The <b>pfnDestroySynchronizationObjectCb</b> function destroys the synchronization object that was created through a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a> function.


## -prototype


````
PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB pfnDestroySynchronizationObjectCb;

__checkReturn HRESULT APIENTRY CALLBACK pfnDestroySynchronizationObjectCb(
  _In_       HANDLE                                hDevice,
  _In_ const D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to a display device (that is, the graphics context).


### -param *








#### - pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_destroysynchronizationobject.md">D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT</a> structure that contains a handle to the synchronization object to destroy.


## -returns



<b>pfnDestroySynchronizationObjectCb</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The synchronization object was successfully destroyed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>
 

This function might also return other HRESULT values.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_destroysynchronizationobject.md">D3DDDICB_DESTROYSYNCHRONIZATIONOBJECT</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createsynchronizationobjectcb.md">pfnCreateSynchronizationObjectCb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYSYNCHRONIZATIONOBJECTCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

