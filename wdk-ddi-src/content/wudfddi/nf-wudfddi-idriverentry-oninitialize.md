---
UID: NF:wudfddi.IDriverEntry.OnInitialize
title: IDriverEntry::OnInitialize
author: windows-driver-content
description: The OnInitialize method performs any operations that are necessary to initialize a driver.
old-location: wdf\idriverentry_oninitialize.htm
tech.root: wdf
ms.assetid: c676588e-348b-4840-9873-6b1bb2454987
ms.date: 2/26/2018
ms.keywords: IDriverEntry interface,OnInitialize method, IDriverEntry.OnInitialize, IDriverEntry::OnInitialize, OnInitialize, OnInitialize method, OnInitialize method,IDriverEntry interface, UMDFDriverObjectRef_01ebb7b4-69bb-4597-b21a-d3ff6cf3bc24.xml, umdf.idriverentry_oninitialize, wdf.idriverentry_oninitialize, wudfddi/IDriverEntry::OnInitialize
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
-	IDriverEntry.OnInitialize
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDriverEntry::OnInitialize


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnInitialize</b> method performs any operations that are necessary to initialize a driver.


## -parameters




### -param pWdfDriver [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a> interface for the framework driver object that represents the driver that is loaded in the host process.


## -returns



<b>OnInitialize</b> returns S_OK if the driver completed its global initialization. Otherwise, this method returns one of the error codes that are defined in Winerror.h. If the driver returns an error code, the framework will not load the driver.




## -remarks



The framework creates a new driver object for each driver that is loaded in the driver host process. When a driver enters the system, the framework calls <b>OnInitialize</b> to notify the driver and passes the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a> interface in the call. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554885">IDriverEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558893">IWDFDriver</a>
 

 

