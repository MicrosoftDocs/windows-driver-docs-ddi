---
UID: NN:wudfddi.IWDFFile
title: IWDFFile
author: windows-driver-content
description: The IWDFFile interface exposes the file object that represents the HANDLE that is returned by the Microsoft Win32 CreateFile function.
old-location: wdf\iwdffile.htm
tech.root: wdf
ms.assetid: bf8e5ab1-9a17-4eb5-8c54-34670ea27068
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFFile, IWDFFile interface, IWDFFile interface,described, UMDFFileObjectRef_41506c7e-3abb-4f41-ab23-a69114c3fdbd.xml, umdf.iwdffile, wdf.iwdffile, wudfddi/IWDFFile
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
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
-	IWDFFile
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFFile interface


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface exposes the file object that represents the HANDLE that is returned by the Microsoft Win32 <b>CreateFile</b> function. All further operations on this handle, such as calls to the Win32 <b>ReadFile</b> function and the <b>DeviceIoControl</b> function, are sent to this file object.


## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFFile</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff560200">IWDFObject</a>. <b>IWDFFile</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>

## -members

The <b>IWDFFile</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558934">IWDFFile::GetDevice</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451305">GetDevice</a> method returns the interface to the device object that a file object is associated with.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558939">IWDFFile::RetrieveFileName</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/7858f3ba-e02a-4115-bf30-12e3a6a75965">RetrieveFileName</a> method retrieves the full name of the file that is associated with the underlying kernel-mode device.

</td>
</tr>
</table> 

