---
UID: NC:videoagp.PAGP_RELEASE_VIRTUAL
title: PAGP_RELEASE_VIRTUAL
author: windows-driver-content
description: The AgpReleaseVirtual function frees system memory reserved by a previous call to AgpReserveVirtual.
old-location: display\agpreleasevirtual.htm
old-project: display
ms.assetid: 4e880b39-e0ee-4801-86b7-ffc06ed415ab
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.agpreleasevirtual, AgpReleaseVirtual callback function [Display Devices], AgpReleaseVirtual, PAGP_RELEASE_VIRTUAL, PAGP_RELEASE_VIRTUAL, videoagp/AgpReleaseVirtual, VideoPort_Functions_4ea0bf12-5d18-4704-9efe-7d8a65a44f1f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: videoagp.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
-	UserDefined
apilocation:
-	videoagp.h
apiname:
-	AgpReleaseVirtual
product: Windows
targetos: Windows
req.typenames: VP_SCATTER_GATHER_LIST, *PVP_SCATTER_GATHER_LIST
req.product: Windows 10 or later.
---

# PAGP_RELEASE_VIRTUAL callback


## -description


The <b>AgpReleaseVirtual</b> function frees system memory reserved by a previous call to <a href="..\videoagp\nc-videoagp-pagp_reserve_virtual.md">AgpReserveVirtual</a>.


## -prototype


````
PAGP_RELEASE_VIRTUAL AgpReleaseVirtual;

VOID APIENTRY AgpReleaseVirtual(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID VirtualReserveContext
)
{ ... }
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param VirtualReserveContext [in]

Is the context handle that identifies the reserved virtual address range to be released. This context was obtained from <b>AgpReleaseVirtual</b>.


## -returns



None




## -remarks



The miniport driver must call <a href="..\videoagp\nc-videoagp-pagp_free_virtual.md">AgpFreeVirtual</a> to unmap all committed memory within the range identified by <b>VirtualReserveContext</b> before calling <b>AgpReleaseVirtual</b> to release it.




## -see-also

<a href="..\videoagp\nc-videoagp-pagp_free_physical.md">AgpFreePhysical</a>



<a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PAGP_RELEASE_VIRTUAL callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

