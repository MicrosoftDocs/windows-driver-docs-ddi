---
UID: NF:wudfddi.IFileCallbackCleanup.OnCleanupFile
title: IFileCallbackCleanup::OnCleanupFile (wudfddi.h)
description: The OnCleanupFile method cancels all I/O requests that a driver has pending in the framework queue.
old-location: wdf\ifilecallbackcleanup_oncleanupfile.htm
tech.root: wdf
ms.assetid: e6dd18f4-725f-4611-ad70-029654cf4375
ms.date: 02/26/2018
ms.keywords: IFileCallbackCleanup interface,OnCleanupFile method, IFileCallbackCleanup.OnCleanupFile, IFileCallbackCleanup::OnCleanupFile, OnCleanupFile, OnCleanupFile method, OnCleanupFile method,IFileCallbackCleanup interface, UMDFFileObjectRef_a264918b-dd98-40e8-b644-d39414c2351c.xml, umdf.ifilecallbackcleanup_oncleanupfile, wdf.ifilecallbackcleanup_oncleanupfile, wudfddi/IFileCallbackCleanup::OnCleanupFile
ms.topic: method
f1_keywords:
 - "wudfddi/IFileCallbackCleanup.OnCleanupFile"
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
- IFileCallbackCleanup.OnCleanupFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IFileCallbackCleanup::OnCleanupFile


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCleanupFile</b> method cancels all I/O requests that a driver has pending in the framework queue. 


## -parameters




### -param pWdfFileObject [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface for the file object that is associated with the device. 


## -remarks



A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ifilecallbackcleanup">IFileCallbackCleanup</a> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 

The framework calls the <b>OnCleanupFile</b> method to notify the driver to cancel all I/O requests that it has pending. The framework notifies the driver in response to an application calling the Microsoft Win32 <b>CloseHandle</b> function. 

For information about when the framework calls <b>OnCleanupFile</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/driver-created-versus-application-created-file-objects">Driver-Created Versus Application-Created File Objects</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ifilecallbackcleanup">IFileCallbackCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a>
 

 

