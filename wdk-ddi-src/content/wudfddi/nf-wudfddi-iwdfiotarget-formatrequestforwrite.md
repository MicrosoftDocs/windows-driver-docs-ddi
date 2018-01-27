---
UID: NF:wudfddi.IWDFIoTarget.FormatRequestForWrite
title: IWDFIoTarget::FormatRequestForWrite method
author: windows-driver-content
description: The FormatRequestForWrite method formats an I/O request object for a write operation.
old-location: wdf\iwdfiotarget_formatrequestforwrite.htm
old-project: wdf
ms.assetid: dd579620-4fe9-4cd0-8e21-f32b07338de1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: umdf.iwdfiotarget_formatrequestforwrite, FormatRequestForWrite method, wudfddi/IWDFIoTarget::FormatRequestForWrite, FormatRequestForWrite, IWDFIoTarget::FormatRequestForWrite, UMDFIoTargetObjectRef_5bd52747-0a43-477e-8240-0481d671a7bb.xml, IWDFIoTarget, FormatRequestForWrite method, IWDFIoTarget interface, IWDFIoTarget interface, FormatRequestForWrite method, wdf.iwdfiotarget_formatrequestforwrite
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
-	IWDFIoTarget.FormatRequestForWrite
product: Windows
targetos: Windows
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoTarget::FormatRequestForWrite method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForWrite</b> method formats an I/O request object for a write operation.


## -syntax


````
HRESULT FormatRequestForWrite(
  [in]           IWDFIoRequest     *pRequest,
  [in, optional] IWDFFile          *pFile,
  [in, optional] IWDFMemory        *pInputMemory,
  [in, optional] PWDFMEMORY_OFFSET pInputMemoryOffset,
  [in, optional] PLONGLONG         DeviceOffset
);
````


## -parameters




### -param pRequest [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface for the request object to format. 


### -param pFile [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface for the file object that is associated with the write request. For the default I/O target, this parameter must be non-<b>NULL</b>.


### -param pInputMemory [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface that is used to access the buffer that is used for the write request. This parameter is optional.


### -param pInputMemoryOffset [in, optional]

A pointer to a <a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure that describes the input memory offset that is used for the write request. This parameter is optional.


### -param DeviceOffset [in, optional]

A pointer to the device offset that is used for the write request. This parameter is optional.


## -returns


<b>FormatRequestForWrite</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. 



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiotarget.md">IWDFIoTarget</a>

<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>

<a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoTarget::FormatRequestForWrite method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

