---
UID: NC:videoagp.PAGP_COMMIT_PHYSICAL
title: PAGP_COMMIT_PHYSICAL
author: windows-driver-content
description: The AgpCommitPhysical function maps system (physical) memory to the specified range of AGP-decodable physical addresses.
old-location: display\agpcommitphysical.htm
old-project: display
ms.assetid: 3c3a6936-7435-4a42-99e6-2c048613af23
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.agpcommitphysical, AgpCommitPhysical callback function [Display Devices], AgpCommitPhysical, PAGP_COMMIT_PHYSICAL, PAGP_COMMIT_PHYSICAL, videoagp/AgpCommitPhysical, VideoPort_Functions_11f78058-194b-4407-b98b-1ae7cd0028f7.xml
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
-	AgpCommitPhysical
product: Windows
targetos: Windows
req.typenames: "*PVP_SCATTER_GATHER_LIST, VP_SCATTER_GATHER_LIST"
req.product: Windows 10 or later.
---

# PAGP_COMMIT_PHYSICAL callback


## -description


The <b>AgpCommitPhysical</b> function maps system (physical) memory to the specified range of AGP-decodable physical addresses.


## -prototype


````
PAGP_COMMIT_PHYSICAL AgpCommitPhysical;

BOOLEAN APIENTRY AgpCommitPhysical(
  _In_ PVOID HwDeviceExtension,
  _In_ PVOID PhysicalReserveContext,
  _In_ ULONG Pages,
  _In_ ULONG Offset
)
{ ... }
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the device extension of the miniport driver.


### -param PhysicalReserveContext [in]

Identifies a reserved physical address range. The context handle is obtained from <a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>.


### -param Pages [in]

Specifies the number of pages of system memory to commit.


### -param Offset [in]

Specifies the page offset at which to commit the pages. The offset is applied to the reserved physical address range associated with <b>PhysicalReserveContext</b>.


## -returns



<b>AgpCommitPhysical</b> returns <b>TRUE</b> if the mapping was successful, and <b>FALSE</b> otherwise.




## -remarks



A video miniport driver must first reserve physical addresses by calling <a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a> before it calls this function.

Do not call <b>AgpCommitPhysical</b> to commit addresses that have already been committed. If the range of pages that is specified by <b>PhysicalReserveContext</b>, <b>Pages</b>, and <b>Offset</b> includes any pages that were previously committed, <b>AgpCommitPhysical</b> might fail.

Video miniport drivers that run on Microsoft Windows 2000 should always reserve and commit a physical range whose size is a multiple of 64 kilobytes. Reserving or committing a physical range that is not a multiple of 64 kilobytes can result in <a href="..\videoagp\nc-videoagp-pagp_reserve_virtual.md">AgpReserveVirtual</a> or <a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a> returning an invalid virtual address.

On Windows XP and later, <b>AgpCommitPhysical</b> automatically expands the committed range so that it is a multiple of 64 kilobytes.

When a video miniport driver calls <b>AgpCommitPhysical</b>, a portion of the physical address range identified by <b>PhysicalReserveContext</b> is mapped to locked pages of physical memory. The mapped portion begins <b>Offset</b> pages into the range identified by <b>PhysicalReserveContext</b>. The video miniport driver can access committed physical memory as if it were contiguous.




## -see-also

<a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>



<a href="..\videoagp\nc-videoagp-pagp_reserve_physical.md">AgpReservePhysical</a>



<a href="..\videoagp\nc-videoagp-pagp_commit_virtual.md">AgpCommitVirtual</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PAGP_COMMIT_PHYSICAL callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

