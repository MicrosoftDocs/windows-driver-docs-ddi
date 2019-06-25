---
UID: NF:wudfddi.IWDFIoTarget.FormatRequestForRead
title: IWDFIoTarget::FormatRequestForRead (wudfddi.h)
description: The FormatRequestForRead method formats an I/O request object for a read operation.
old-location: wdf\iwdfiotarget_formatrequestforread.htm
tech.root: wdf
ms.assetid: 8a1b61c8-8b85-4224-ae20-3788eb0babe4
ms.date: 02/26/2018
ms.keywords: FormatRequestForRead, FormatRequestForRead method, FormatRequestForRead method,IWDFIoTarget interface, IWDFIoTarget interface,FormatRequestForRead method, IWDFIoTarget.FormatRequestForRead, IWDFIoTarget::FormatRequestForRead, UMDFIoTargetObjectRef_49d4b6d7-0cd7-4d8a-9b16-7ecc89f82f1e.xml, umdf.iwdfiotarget_formatrequestforread, wdf.iwdfiotarget_formatrequestforread, wudfddi/IWDFIoTarget::FormatRequestForRead
ms.topic: method
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
- IWDFIoTarget.FormatRequestForRead
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTarget::FormatRequestForRead


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForRead</b> method formats an I/O request object for a read operation.


## -parameters




### -param pRequest [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a> interface for the request object to format. 


### -param pFile [in, optional]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface for the file object that is associated with the read request. For the default I/O target, this parameter must be non-NULL.


### -param pOutputMemory [in, optional]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a> interface that is used to access the buffer that is used for the read request. This parameter is optional.


### -param pOutputMemoryOffset [in, optional]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ns-wudfddi_types-_wdfmemory_offset">WDFMEMORY_OFFSET</a> structure that describes the output memory offset that is used for the read. This parameter is optional.


### -param DeviceOffset [in, optional]

A pointer to the device offset that is used for the read. This parameter is optional.


## -returns



<b>FormatRequestForRead</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiorequest">IWDFIoRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfiotarget">IWDFIoTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi/nn-wudfddi-iwdfmemory">IWDFMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wudfddi_types/ns-wudfddi_types-_wdfmemory_offset">WDFMEMORY_OFFSET</a>
 

 

