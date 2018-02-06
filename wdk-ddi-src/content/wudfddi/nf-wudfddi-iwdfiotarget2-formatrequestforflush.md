---
UID: NF:wudfddi.IWDFIoTarget2.FormatRequestForFlush
title: IWDFIoTarget2::FormatRequestForFlush method
author: windows-driver-content
description: The FormatRequestForFlush method builds an I/O request for a flush operation but does not send the request to an I/O target.
old-location: wdf\iwdfiotarget2_formatrequestforflush.htm
old-project: wdf
ms.assetid: 28509e28-0e81-4531-947c-9ce452564682
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: umdf.iwdfiotarget2_formatrequestforflush, IWDFIoTarget2::FormatRequestForFlush, FormatRequestForFlush method, FormatRequestForFlush method, IWDFIoTarget2 interface, FormatRequestForFlush, wdf.iwdfiotarget2_formatrequestforflush, IWDFIoTarget2 interface, FormatRequestForFlush method, wudfddi/IWDFIoTarget2::FormatRequestForFlush, UMDFIoTargetObjectRef_985162ca-fae2-408e-b4df-59add8e4a760.xml, IWDFIoTarget2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
-	IWDFIoTarget2.FormatRequestForFlush
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFIoTarget2::FormatRequestForFlush method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>FormatRequestForFlush</b> method builds an I/O request for a flush operation but does not send the request to an I/O target.


## -syntax


````
HRESULT FormatRequestForFlush(
  [in]           IWDFIoRequest *pRequest,
  [in, optional] IWDFFile      *pFile
);
````


## -parameters




### -param pRequest [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface of the request object that represents the I/O request. 


### -param pFile [in, optional]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface of the file object that is associated with the I/O request. This parameter is optional and can be <b>NULL</b>, but it is required for the default I/O target.


## -returns


<b>FormatRequestForFlush</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following value:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">
The framework was unable to allocate memory.

</td>
</tr>
</table> 

This method might return one of the other values that Winerror.h contains.



## -remarks


Some drivers must flush cached buffers that exist in either a lower driver or the device. For example, drivers that exist in a driver stack for a serial device or a storage device might support this operation. 

Use the <b>FormatRequestForFlush</b> method, followed by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> method, to send flush requests either synchronously or asynchronously. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556847">IQueueCallbackDefaultIoHandler::OnDefaultIoHandler</a>

<a href="..\wudfddi\nn-wudfddi-iwdfiotarget2.md">IWDFIoTarget2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoTarget2::FormatRequestForFlush method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

