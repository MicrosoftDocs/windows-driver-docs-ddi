---
UID: NF:wudfddi.IWDFIoTarget.FormatRequestForIoctl
title: IWDFIoTarget::FormatRequestForIoctl
author: windows-driver-content
description: The FormatRequestForIoctl method formats an I/O request object for an I/O control operation.
old-location: wdf\iwdfiotarget_formatrequestforioctl.htm
tech.root: wdf
ms.assetid: fd0bbd6e-bb23-4d0c-9cac-9bb7657876a0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: FormatRequestForIoctl, FormatRequestForIoctl method, FormatRequestForIoctl method,IWDFIoTarget interface, IWDFIoTarget interface,FormatRequestForIoctl method, IWDFIoTarget.FormatRequestForIoctl, IWDFIoTarget::FormatRequestForIoctl, UMDFIoTargetObjectRef_9c72ba41-4a3f-4bea-8ca1-bcf04dd033ad.xml, umdf.iwdfiotarget_formatrequestforioctl, wdf.iwdfiotarget_formatrequestforioctl, wudfddi/IWDFIoTarget::FormatRequestForIoctl
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoTarget.FormatRequestForIoctl
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTarget::FormatRequestForIoctl


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForIoctl</b> method formats an I/O request object for an I/O control operation.


## -parameters




### -param pRequest [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a> interface for the request object to format. 


### -param IoctlCode [in]

A control code that identifies a specific operation to perform.


### -param pFile [in, optional]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface for the file object that is associated with the I/O control request. For the default I/O target, this parameter must be non-NULL.


### -param pInputMemory [in, optional]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface that is used to access the input buffer for the request. This parameter is optional.


### -param pInputMemoryOffset [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a> structure that describes the input memory offset for the request. This parameter is optional.


### -param pOutputMemory [in, optional]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a> interface that is used to access the output buffer for the request. This parameter is optional.


### -param pOutputMemoryOffset [in, optional]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a> structure that describes the output memory offset for the request. This parameter is optional.


## -returns



<b>FormatRequestForIoctl</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559249">IWDFMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561398">WDFMEMORY_OFFSET</a>
 

 

