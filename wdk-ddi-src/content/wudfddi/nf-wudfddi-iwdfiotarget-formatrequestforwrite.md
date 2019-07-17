---
UID: NF:wudfddi.IWDFIoTarget.FormatRequestForWrite
title: IWDFIoTarget::FormatRequestForWrite (wudfddi.h)
description: The FormatRequestForWrite method formats an I/O request object for a write operation.
old-location: wdf\iwdfiotarget_formatrequestforwrite.htm
tech.root: wdf
ms.assetid: dd579620-4fe9-4cd0-8e21-f32b07338de1
ms.date: 02/26/2018
ms.keywords: FormatRequestForWrite, FormatRequestForWrite method, FormatRequestForWrite method,IWDFIoTarget interface, IWDFIoTarget interface,FormatRequestForWrite method, IWDFIoTarget.FormatRequestForWrite, IWDFIoTarget::FormatRequestForWrite, UMDFIoTargetObjectRef_5bd52747-0a43-477e-8240-0481d671a7bb.xml, umdf.iwdfiotarget_formatrequestforwrite, wdf.iwdfiotarget_formatrequestforwrite, wudfddi/IWDFIoTarget::FormatRequestForWrite
ms.topic: method
f1_keywords:
 - "wudfddi/IWDFIoTarget.FormatRequestForWrite"
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFIoTarget.FormatRequestForWrite
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTarget::FormatRequestForWrite


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForWrite</b> method formats an I/O request object for a write operation.


## -parameters




### -param pRequest [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface for the request object to format. 


### -param pFile [in, optional]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface for the file object that is associated with the write request. For the default I/O target, this parameter must be non-<b>NULL</b>.


### -param pInputMemory [in, optional]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface that is used to access the buffer that is used for the write request. This parameter is optional.


### -param pInputMemoryOffset [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ns-wudfddi_types-_wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that describes the input memory offset that is used for the write request. This parameter is optional.


### -param DeviceOffset [in, optional]

A pointer to the device offset that is used for the write request. This parameter is optional.


## -returns



<b>FormatRequestForWrite</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiotarget">IWDFIoTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ns-wudfddi_types-_wdfmemory_offset">WDFMEMORY_OFFSET</a>
 

 

