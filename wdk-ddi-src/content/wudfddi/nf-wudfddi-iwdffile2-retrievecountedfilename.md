---
UID: NF:wudfddi.IWDFFile2.RetrieveCountedFileName
title: IWDFFile2::RetrieveCountedFileName method
author: windows-driver-content
description: The RetrieveCountedFileName method retrieves the full counted file name for a file that is associated with a device.
old-location: wdf\iwdffile2_retrievecountedfilename.htm
old-project: wdf
ms.assetid: 0b3aa8d9-1947-4e5e-91d1-6f73ddb3908a
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFFile2, IWDFFile2::RetrieveCountedFileName, RetrieveCountedFileName
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
req.alt-api: IWDFFile2.RetrieveCountedFileName
req.alt-loc: WUDFx.dll
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
req.typenames: *PPOWER_ACTION, POWER_ACTION
req.product: Windows 10 or later.
---

# IWDFFile2::RetrieveCountedFileName method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveCountedFileName</b> method retrieves the full counted file name for a file that is associated with a device. 



## -syntax

````
HRESULT RetrieveCountedFileName(
  [out]     WCHAR *pCountedFileName,
  [in, out] DWORD *pdwCountedFileNameLength
);
````


## -parameters

### -param pCountedFileName [out]

A pointer to a caller-allocated buffer. This buffer receives a <b>NULL</b>-terminated character string that represents the full name of the file that is associated with the device. If the pointer is <b>NULL</b>, <b>RetrieveCountedFileName</b> retrieves only the string length. 


### -param pdwCountedFileNameLength [in, out]

A pointer to a caller-allocated variable. On input, the driver sets the variable to the length, in characters, of the buffer that <i>pdwFileNameLengthInChars</i> points to. On output, the framework sets the variable to the length, in characters, of the character string (including the terminating <b>NULL</b> character) that it placed in the buffer. If a counted file name does not exist, the framework sets the variable to zero. 


## -returns
<b>RetrieveCountedFileName</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values:
<dl>
<dt><b>E_POINTER</b></dt>
</dl>The <i>pdwCountedFileNameLength</i> pointer is <b>NULL</b>.
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_PARAMETER)</b></dt>
</dl>The counted file name is invalid.
<dl>
<dt><b>E_NOT_SUFFICIENT_BUFFER</b></dt>
</dl>The buffer that <i>pCountedFileName</i> points to is too small.

 

This method might return one of the other values that Winerror.h contains.


## -remarks
A counted file name is a string that can include embedded <b>NULL</b> ('\0') characters in addition to a terminating <b>NULL</b>. To obtain a name string without embedded <b>NULL</b> characters, drivers can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558939">IWDFFile::RetrieveFileName</a>.

Typically, a driver calls <b>RetrieveCountedFileName</b> twice, using the following steps:

The driver calls <b>RetrieveCountedFileName</b> with the <i>pCountedFileName</i> parameter set to <b>NULL</b>, to obtain the required buffer length.

The driver allocates a buffer of the required size.

The driver calls <b>RetrieveCountedFileName</b> again to obtain the file name string.

The following code example obtains the <a href="..\wudfddi\nn-wudfddi-iwdffile2.md">IWDFFile2</a> interface from the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface that a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a> callback function receives. The example calls <b>RetrieveCountedFileName</b> twice--once to obtain the file name's length and once to retrieve the file name string.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdffile2.md">IWDFFile2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558939">IWDFFile::RetrieveFileName</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFFile2::RetrieveCountedFileName method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

