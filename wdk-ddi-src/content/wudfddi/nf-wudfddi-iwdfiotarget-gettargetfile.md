---
UID: NF:wudfddi.IWDFIoTarget.GetTargetFile
title: IWDFIoTarget::GetTargetFile (wudfddi.h)
description: The GetTargetFile method retrieves the framework file object that is associated with the I/O target object.
old-location: wdf\iwdfiotarget_gettargetfile.htm
tech.root: wdf
ms.assetid: d38ede60-9bcf-4c90-8c41-8f1edf1a1d23
ms.date: 02/26/2018
ms.keywords: GetTargetFile, GetTargetFile method, GetTargetFile method,IWDFIoTarget interface, IWDFIoTarget interface,GetTargetFile method, IWDFIoTarget.GetTargetFile, IWDFIoTarget::GetTargetFile, UMDFIoTargetObjectRef_c31a719b-616e-4559-851a-a9f5c35bc9e5.xml, umdf.iwdfiotarget_gettargetfile, wdf.iwdfiotarget_gettargetfile, wudfddi/IWDFIoTarget::GetTargetFile
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
-	IWDFIoTarget.GetTargetFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFIoTarget::GetTargetFile


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetTargetFile</b> method retrieves the framework file object that is associated with the I/O target object.


## -parameters




### -param ppWdfFile






#### - ppFileObject [out]

Pointer to a buffer that receives a pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface for the I/O target's file object.


## -returns



None




## -remarks



If  a framework file object is associated with an I/O target object, the framework includes the file object  with I/O requests that  the driver sends to the I/O target object. 

When a driver formats an I/O request, an I/O target object enables the driver to use either the same file that the request started with or a new file.

The default I/O target has no file object, so a call to <b>GetTargetFile</b> for the default I/O target retrieves <b>NULL</b>. 

For more information about I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-i-o-targets-in-umdf">Using I/O Targets in UMDF</a>.


#### Examples

For a code example of how to use the <b>GetTargetFile</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559236">IWDFIoTarget::FormatRequestForWrite</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559170">IWDFIoTarget</a>
 

 

