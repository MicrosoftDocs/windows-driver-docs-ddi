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
ms.keywords: umdf.iwdffile2_retrievecountedfilename, RetrieveCountedFileName, RetrieveCountedFileName method, IWDFFile2::RetrieveCountedFileName, UMDFFileObjectRef_89204c8a-3847-4e03-bf8b-c660b1b2408b.xml, wudfddi/IWDFFile2::RetrieveCountedFileName, IWDFFile2, RetrieveCountedFileName method, IWDFFile2 interface, wdf.iwdffile2_retrievecountedfilename, IWDFFile2 interface, RetrieveCountedFileName method
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
-	IWDFFile2.RetrieveCountedFileName
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
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


### -param pdwCountedFileNameLengthInChars






#### - pdwCountedFileNameLength [in, out]

A pointer to a caller-allocated variable. On input, the driver sets the variable to the length, in characters, of the buffer that <i>pdwFileNameLengthInChars</i> points to. On output, the framework sets the variable to the length, in characters, of the character string (including the terminating <b>NULL</b> character) that it placed in the buffer. If a counted file name does not exist, the framework sets the variable to zero. 


## -returns



<b>RetrieveCountedFileName</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
The <i>pdwCountedFileNameLength</i> pointer is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_PARAMETER)</b></dt>
</dl>
</td>
<td width="60%">
The counted file name is invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOT_SUFFICIENT_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
The buffer that <i>pCountedFileName</i> points to is too small.

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.




## -remarks



A counted file name is a string that can include embedded <b>NULL</b> ('\0') characters in addition to a terminating <b>NULL</b>. To obtain a name string without embedded <b>NULL</b> characters, drivers can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558939">IWDFFile::RetrieveFileName</a>.

Typically, a driver calls <b>RetrieveCountedFileName</b> twice, using the following steps:

<ol>
<li>
The driver calls <b>RetrieveCountedFileName</b> with the <i>pCountedFileName</i> parameter set to <b>NULL</b>, to obtain the required buffer length.

</li>
<li>
The driver allocates a buffer of the required size.

</li>
<li>
The driver calls <b>RetrieveCountedFileName</b> again to obtain the file name string.

</li>
</ol>

#### Examples

The following code example obtains the <a href="..\wudfddi\nn-wudfddi-iwdffile2.md">IWDFFile2</a> interface from the <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface that a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a> callback function receives. The example calls <b>RetrieveCountedFileName</b> twice--once to obtain the file name's length and once to retrieve the file name string.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
STDMETHODCALLTYPE
CMyQueue::OnCreateFile(
    __in IWDFIoQueue *pWdfQueue,
    __in IWDFIoRequest *pWdfRequest,
    __in IWDFFile*  pWdfFileObject
    )
 ...
    IWDFFile2*  pWdfFileObject2 = NULL;
    WCHAR*  countedFileName = NULL;
    DWORD  countedFileNameCch = 0;
    HRESULT  hr = S_OK;
 
    //
    // Obtain IWDFFile2 interface from IWDFFile.
    //
    hr = pWdfFileObject-&gt;QueryInterface(IID_PPV_ARGS(&amp;pWdfFileObject2));
    if (!SUCCEEDED(hr))
    {
        goto Done;
    }
    //
    // Get length of counted filename.
    //
    hr = pWdfFileObject2-&gt;RetrieveCountedFileName(NULL,
                                                  &amp;countedFileNameCch);
    if (!SUCCEEDED(hr))
    {
        goto Done;
    }
    if (countedFileNameCch != 0)
    {
        //
        // Allocate a buffer.
        //
        countedFileName = new WCHAR[countedFileNameCch];
        if (countedFileName == NULL)
        {
            hr = E_OUTOFMEMORY;
            goto Done;
        }
        //
        // Get counted file name.
        //
        hr = pWdfFileObject2-&gt;RetrieveCountedFileName(countedFileName, 
                                                      &amp;countedFileNameCch);
        if (!SUCCEEDED(hr))
        {
            goto Done;
        }
    }
    ...</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558939">IWDFFile::RetrieveFileName</a>



<a href="..\wudfddi\nn-wudfddi-iwdffile2.md">IWDFFile2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFFile2::RetrieveCountedFileName method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

