---
UID: NF:wudfddi.IFileCallbackClose.OnCloseFile
title: IFileCallbackClose::OnCloseFile (wudfddi.h)
description: The OnCloseFile method is called when the last reference count on a file object goes down to zero and before the file object is released.
old-location: wdf\ifilecallbackclose_onclosefile.htm
tech.root: wdf
ms.assetid: ca3bd7af-b270-497e-a90a-6d79ce66d968
ms.date: 02/26/2018
keywords: ["IFileCallbackClose::OnCloseFile"]
ms.keywords: IFileCallbackClose interface,OnCloseFile method, IFileCallbackClose.OnCloseFile, IFileCallbackClose::OnCloseFile, OnCloseFile, OnCloseFile method, OnCloseFile method,IFileCallbackClose interface, UMDFFileObjectRef_8aa60206-80e0-4c49-b2fd-c79f5e703c18.xml, umdf.ifilecallbackclose_onclosefile, wdf.ifilecallbackclose_onclosefile, wudfddi/IFileCallbackClose::OnCloseFile
f1_keywords:
 - "wudfddi/IFileCallbackClose.OnCloseFile"
 - "IFileCallbackClose.OnCloseFile"
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
- IFileCallbackClose.OnCloseFile
targetos: Windows
req.typenames: 
---

# IFileCallbackClose::OnCloseFile


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnCloseFile</b> method is called when the last reference count on a file object goes down to zero and before the file object is released. 


## -parameters




### -param pWdfFileObject [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface for the file object that is associated with the device. 


## -remarks



A driver registers the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ifilecallbackclose">IFileCallbackClose</a> interface when the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 

For information about when the framework calls <b>OnCloseFile</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/driver-created-versus-application-created-file-objects">Driver-Created Versus Application-Created File Objects</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ifilecallbackclose">IFileCallbackClose</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdriver-createdevice">IWDFDriver::CreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a>
 

 

