---
UID: NF:wudfddi.IDriverEntry.OnDeinitialize
title: IDriverEntry::OnDeinitialize method
author: windows-driver-content
description: The OnDeinitialize method performs any operations that are necessary before a system unloads a driver.
old-location: wdf\idriverentry_ondeinitialize.htm
old-project: wdf
ms.assetid: 9366029e-4f8b-4121-ad99-01a5116a7f46
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IDriverEntry, IDriverEntry interface, OnDeinitialize method, IDriverEntry::OnDeinitialize, OnDeinitialize method, OnDeinitialize method, IDriverEntry interface, OnDeinitialize,IDriverEntry.OnDeinitialize, UMDFDriverObjectRef_0dc59f06-5979-4077-8945-b0568d8980ba.xml, umdf.idriverentry_ondeinitialize, wdf.idriverentry_ondeinitialize, wudfddi/IDriverEntry::OnDeinitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IDriverEntry.OnDeinitialize
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IDriverEntry::OnDeinitialize method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnDeinitialize</b> method performs any operations that are necessary before a system unloads a driver.


## -parameters




### -param pWdfDriver [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a> interface for the driver object that represents the driver that the system unloads.


## -returns



None




## -remarks



The framework creates a new driver object for each driver that is loaded in the driver host process. When a driver is about to be unloaded from the host process, the framework calls <b>OnDeinitialize</b> to notify the driver of the departure and passes the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a> interface in the call. The system unloads the driver after <b>OnDeinitialize</b> returns. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554885">IDriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a>
 

 

