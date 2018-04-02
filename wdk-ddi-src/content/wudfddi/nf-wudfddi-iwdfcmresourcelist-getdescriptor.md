---
UID: NF:wudfddi.IWDFCmResourceList.GetDescriptor
title: IWDFCmResourceList::GetDescriptor method
author: windows-driver-content
description: The GetDescriptor method returns a pointer to a resource descriptor that is contained in this interface's resource list.
old-location: wdf\iwdfcmresourcelist_getdescriptor.htm
old-project: wdf
ms.assetid: 5E870D10-A03B-4CD8-A2DD-54A6AB527DB2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetDescriptor method, GetDescriptor method, IWDFCmResourceList interface, GetDescriptor,IWDFCmResourceList.GetDescriptor, IWDFCmResourceList, IWDFCmResourceList interface, GetDescriptor method, IWDFCmResourceList::GetDescriptor, umdf.iwdfcmresourcelist_getdescriptor, wdf.iwdfcmresourcelist_getdescriptor, wudfddi/IWDFCmResourceList::GetDescriptor
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
-	IWDFCmResourceList.GetDescriptor
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFCmResourceList::GetDescriptor method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <b>GetDescriptor</b> method returns a pointer to a resource descriptor that is contained in this interface's resource list.




## -parameters




### -param Index

A zero-based index into the logical configuration that is contained in this interface's resource list.


## -returns



<b>GetDescriptor</b> returns a pointer to a <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure.




## -remarks



Drivers typically call <b>GetDescriptor</b> from within <a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a>, before calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh451225">MapIoSpace</a>.

The <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure  is defined in Wudfwdm.h.

For more information about parsing hardware resources, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources-in-umdf-1-x-drivers">Finding and Mapping Hardware Resources in a UMDF Driver</a>.


#### Examples

See example code in <a href="https://msdn.microsoft.com/243C7299-7C74-408A-8FB9-32FB3315251F">IWDFDevice3::MapIoSpace</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439762">IWDFCmResourceList</a>
 

 

