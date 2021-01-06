---
UID: NN:wudfddi.IWDFFile
title: IWDFFile (wudfddi.h)
description: The IWDFFile interface exposes the file object that represents the HANDLE that is returned by the Microsoft Win32 CreateFile function.
old-location: wdf\iwdffile.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFFile interface"]
ms.keywords: IWDFFile, IWDFFile interface, IWDFFile interface,described, UMDFFileObjectRef_41506c7e-3abb-4f41-ab23-a69114c3fdbd.xml, umdf.iwdffile, wdf.iwdffile, wudfddi/IWDFFile
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFFile
 - wudfddi/IWDFFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFFile
---

# IWDFFile interface


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface exposes the file object that represents the HANDLE that is returned by the Microsoft Win32 <b>CreateFile</b> function. All further operations on this handle, such as calls to the Win32 <b>ReadFile</b> function and the <b>DeviceIoControl</b> function, are sent to this file object.

## -inheritance

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFFile</b> interface inherits from <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfobject">IWDFObject</a>. <b>IWDFFile</b> also has these types of members:
<ul>
<li><a href="https://docs.microsoft.com/">Methods</a></li>
</ul>
