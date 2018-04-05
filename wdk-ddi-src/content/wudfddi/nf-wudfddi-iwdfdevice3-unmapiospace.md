---
UID: NF:wudfddi.IWDFDevice3.UnmapIoSpace
title: IWDFDevice3::UnmapIoSpace method
author: windows-driver-content
description: The UnmapIoSpace method unmaps a specified range of physical addresses previously mapped by MapIoSpace method.
old-location: wdf\iwdfdevice3_unmapiospace.htm
old-project: wdf
ms.assetid: E95AC8E6-222A-4C88-8EBD-6BD7F22B9F18
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFDevice3, IWDFDevice3 interface, UnmapIoSpace method, IWDFDevice3::UnmapIoSpace, UnmapIoSpace method, UnmapIoSpace method, IWDFDevice3 interface, UnmapIoSpace,IWDFDevice3.UnmapIoSpace, umdf.iwdfdevice3_unmapiospace, wdf.iwdfdevice3_unmapiospace, wudfddi/IWDFDevice3::UnmapIoSpace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDevice3.UnmapIoSpace
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice3::UnmapIoSpace method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>UnmapIoSpace</b> method unmaps a specified range of physical addresses previously mapped by <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a> method.


## -parameters




### -param PseudoBaseAddress [in]

Pointer to the pseudo base address obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a> method to which the physical address range was mapped.


### -param NumberOfBytes [in]

Specifies the number of bytes that were mapped.


## -returns



This method does not return a value.




## -remarks



If a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a> in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a> callback. It calls <b>UnmapIoSpace</b> in its <a href="https://msdn.microsoft.com/library/windows/hardware/hh439739">OnReleaseHardware</a> callback.

For an example, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.


#### Examples

See example code in <a href="https://msdn.microsoft.com/243C7299-7C74-408A-8FB9-32FB3315251F">IWDFDevice3::MapIoSpace</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh451197">IWDFDevice3</a>
 

 

