---
UID: NS:d3dkmddi._DXGK_MONITORDESCRIPTORSET_INTERFACE
title: "_DXGK_MONITORDESCRIPTORSET_INTERFACE"
author: windows-driver-content
description: The DXGK_MONITORDESCRIPTORSET_INTERFACE structure contains pointers to functions that belong to the Monitor Descriptor Set Interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitordescriptorset_interface.htm
old-project: display
ms.assetid: ac492a44-f14e-4b66-9ec1-4f1b04806646
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, A, C, D, DXGK_MONITORDESCRIPTORSET_INTERFACE, DXGK_MONITORDESCRIPTORSET_INTERFACE structure [Display Devices], DmStructs_da0cca60-6df0-480b-8e02-0affe5eb5cfd.xml, E, F, G, I, K, M, N, O, P, R, S, T, X, _, _DXGK_MONITORDESCRIPTORSET_INTERFACE, d3dkmddi/DXGK_MONITORDESCRIPTORSET_INTERFACE, display.dxgk_monitordescriptorset_interface"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGK_MONITORDESCRIPTORSET_INTERFACE
product: Windows
targetos: Windows
req.typenames: DXGK_MONITORDESCRIPTORSET_INTERFACE
---

# _DXGK_MONITORDESCRIPTORSET_INTERFACE structure


## -description


The DXGK_MONITORDESCRIPTORSET_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568427">Monitor Descriptor Set Interface</a>, which is implemented by the video present network (VidPN) manager.


## -syntax


````
typedef struct _DXGK_MONITORDESCRIPTORSET_INTERFACE {
  DXGKDDI_MONITORDESCRIPTORSET_GETNUMDESCRIPTORS          pfnGetNumDescriptors;
  DXGKDDI_MONITORDESCRIPTORSET_ACQUIREFIRSTDESCRIPTORINFO pfnAcquireFirstDescriptorInfo;
  DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO  pfnAcquireNextDescriptorInfo;
  DXGKDDI_MONITORDESCRIPTORSET_RELEASEDESCRIPTORINFO      pfnReleaseDescriptorInfo;
} DXGK_MONITORDESCRIPTORSET_INTERFACE;
````


## -struct-fields




### -field pfnGetNumDescriptors

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_getnumdescriptors.md">pfnGetNumDescriptors</a> function. 


### -field pfnAcquireFirstDescriptorInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirefirstdescriptorinfo.md">pfnAcquireFirstDescriptorInfo</a> function.


### -field pfnAcquireNextDescriptorInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirenextdescriptorinfo.md">pfnAcquireNextDescriptorInfo</a> function. 


### -field pfnReleaseDescriptorInfo

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_releasedescriptorinfo.md">pfnReleaseDescriptorInfo</a> function. 


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirefirstdescriptorinfo.md">pfnAcquireFirstDescriptorInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_getnumdescriptors.md">pfnGetNumDescriptors</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_releasedescriptorinfo.md">pfnReleaseDescriptorInfo</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirenextdescriptorinfo.md">pfnAcquireNextDescriptorInfo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MONITORDESCRIPTORSET_INTERFACE structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

