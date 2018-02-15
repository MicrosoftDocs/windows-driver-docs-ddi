---
UID: NF:wudfddi.IWDFIoTarget.FormatRequestForIoctl
title: IWDFIoTarget::FormatRequestForIoctl method
author: windows-driver-content
description: The FormatRequestForIoctl method formats an I/O request object for an I/O control operation.
old-location: wdf\iwdfiotarget_formatrequestforioctl.htm
old-project: wdf
ms.assetid: fd0bbd6e-bb23-4d0c-9cac-9bb7657876a0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFIoTarget, wudfddi/IWDFIoTarget::FormatRequestForIoctl, wdf.iwdfiotarget_formatrequestforioctl, FormatRequestForIoctl method, IWDFIoTarget interface, UMDFIoTargetObjectRef_9c72ba41-4a3f-4bea-8ca1-bcf04dd033ad.xml, FormatRequestForIoctl method, umdf.iwdfiotarget_formatrequestforioctl, IWDFIoTarget interface, FormatRequestForIoctl method, FormatRequestForIoctl, IWDFIoTarget::FormatRequestForIoctl
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
-	IWDFIoTarget.FormatRequestForIoctl
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFIoTarget::FormatRequestForIoctl method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForIoctl</b> method formats an I/O request object for an I/O control operation.


## -syntax


````
HRESULT FormatRequestForIoctl(
  [in]           IWDFIoRequest     *pRequest,
  [in]           ULONG             IoctlCode,
  [in, optional] IWDFFile          *pFile,
  [in, optional] IWDFMemory        *pInputMemory,
  [in, optional] PWDFMEMORY_OFFSET pInputMemoryOffset,
  [in, optional] IWDFMemory        *pOutputMemory,
  [in, optional] PWDFMEMORY_OFFSET pOutputMemoryOffset
);
````


## -parameters




### -param pRequest [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface for the request object to format. 


### -param IoctlCode [in]

A control code that identifies a specific operation to perform.


### -param pFile [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface for the file object that is associated with the I/O control request. For the default I/O target, this parameter must be non-NULL.


### -param pInputMemory [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface that is used to access the input buffer for the request. This parameter is optional.


### -param pInputMemoryOffset [in, optional]

A pointer to a <a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure that describes the input memory offset for the request. This parameter is optional.


### -param pOutputMemory [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a> interface that is used to access the output buffer for the request. This parameter is optional.


### -param pOutputMemoryOffset [in, optional]

A pointer to a <a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a> structure that describes the output memory offset for the request. This parameter is optional.


## -returns



<b>FormatRequestForIoctl</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h. 




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>



<a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a>



<a href="..\wudfddi_types\ns-wudfddi_types-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>



<a href="..\wudfddi\nn-wudfddi-iwdfmemory.md">IWDFMemory</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiotarget.md">IWDFIoTarget</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoTarget::FormatRequestForIoctl method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

