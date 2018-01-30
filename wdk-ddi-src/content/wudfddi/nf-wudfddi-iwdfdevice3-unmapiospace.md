---
UID: NF:wudfddi.IWDFDevice3.UnmapIoSpace
title: IWDFDevice3::UnmapIoSpace method
author: windows-driver-content
description: The UnmapIoSpace method unmaps a specified range of physical addresses previously mapped by MapIoSpace method.
old-location: wdf\iwdfdevice3_unmapiospace.htm
old-project: wdf
ms.assetid: E95AC8E6-222A-4C88-8EBD-6BD7F22B9F18
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDevice3, UnmapIoSpace, wudfddi/IWDFDevice3::UnmapIoSpace, umdf.iwdfdevice3_unmapiospace, IWDFDevice3::UnmapIoSpace, UnmapIoSpace method, wdf.iwdfdevice3_unmapiospace, UnmapIoSpace method, IWDFDevice3 interface, IWDFDevice3 interface, UnmapIoSpace method
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
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	WUDFx.dll
apiname:
-	IWDFDevice3.UnmapIoSpace
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFDevice3::UnmapIoSpace method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>UnmapIoSpace</b> method unmaps a specified range of physical addresses previously mapped by <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a> method.


## -syntax


````
VOID UnmapIoSpace(
  [in] PVOID  *PseudoBaseAddress,
  [in] SIZE_T NumberOfBytes
);
````


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



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice3::UnmapIoSpace method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

