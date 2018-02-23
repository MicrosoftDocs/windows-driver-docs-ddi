---
UID: NC:d3dumddi.PFND3DDDI_EVICTCB
title: PFND3DDDI_EVICTCB
author: windows-driver-content
description: pfnEvictCb is used to instruct the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.
old-location: display\pfnevictcb.htm
old-project: display
ms.assetid: 5E66A522-BC1C-4E7C-8732-87D40F99BBDA
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.pfnevictcb, pfnEvictCb callback function [Display Devices], pfnEvictCb, PFND3DDDI_EVICTCB, PFND3DDDI_EVICTCB, d3dumddi/pfnEvictCb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	pfnEvictCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_EVICTCB callback


## -description


<b>pfnEvictCb</b> is used to instruct the OS to decrement the residency reference count. Once this count reaches zero, it will remove the allocation from the device residency list.


## -prototype


````
PFND3DDDI_EVICTCB pfnEvictCb;

HRESULT APIENTRY CALLBACK* pfnEvictCb(
  _In_    HANDLE         hDevice,
  _Inout_ D3DDDICB_EVICT *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








#### - pData [in, out]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-d3dddicb_evict.md">D3DDDICB_EVICT</a> structure that describes the memory pages to evict.




## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -remarks



Once the eviction request is queued, it is illegal to access the underlying allocation as the allocation may be evicted at anytime from there on at the operating system discretion.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-d3dddicb_evict.md">D3DDDICB_EVICT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_EVICTCB callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

