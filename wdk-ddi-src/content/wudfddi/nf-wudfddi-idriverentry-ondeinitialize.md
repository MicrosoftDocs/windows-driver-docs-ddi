---
UID: NF:wudfddi.IDriverEntry.OnDeinitialize
title: IDriverEntry::OnDeinitialize (wudfddi.h)
description: The OnDeinitialize method performs any operations that are necessary before a system unloads a driver.
old-location: wdf\idriverentry_ondeinitialize.htm
tech.root: wdf
ms.assetid: 9366029e-4f8b-4121-ad99-01a5116a7f46
ms.date: 02/26/2018
keywords: ["IDriverEntry::OnDeinitialize"]
ms.keywords: IDriverEntry interface,OnDeinitialize method, IDriverEntry.OnDeinitialize, IDriverEntry::OnDeinitialize, OnDeinitialize, OnDeinitialize method, OnDeinitialize method,IDriverEntry interface, UMDFDriverObjectRef_0dc59f06-5979-4077-8945-b0568d8980ba.xml, umdf.idriverentry_ondeinitialize, wdf.idriverentry_ondeinitialize, wudfddi/IDriverEntry::OnDeinitialize
f1_keywords:
 - "wudfddi/IDriverEntry.OnDeinitialize"
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IDriverEntry.OnDeinitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDriverEntry::OnDeinitialize


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnDeinitialize</b> method performs any operations that are necessary before a system unloads a driver.


## -parameters




### -param pWdfDriver [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdriver">IWDFDriver</a> interface for the driver object that represents the driver that the system unloads.


## -remarks



The framework creates a new driver object for each driver that is loaded in the driver host process. When a driver is about to be unloaded from the host process, the framework calls <b>OnDeinitialize</b> to notify the driver of the departure and passes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdriver">IWDFDriver</a> interface in the call. The system unloads the driver after <b>OnDeinitialize</b> returns. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-idriverentry">IDriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfdriver">IWDFDriver</a>
 

 

