---
UID: NF:wudfddi.IWDFFile2.RetrieveCountedFileName
title: IWDFFile2::RetrieveCountedFileName (wudfddi.h)
description: The RetrieveCountedFileName method retrieves the full counted file name for a file that is associated with a device.
old-location: wdf\iwdffile2_retrievecountedfilename.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["IWDFFile2::RetrieveCountedFileName"]
ms.keywords: IWDFFile2 interface,RetrieveCountedFileName method, IWDFFile2.RetrieveCountedFileName, IWDFFile2::RetrieveCountedFileName, RetrieveCountedFileName, RetrieveCountedFileName method, RetrieveCountedFileName method,IWDFFile2 interface, UMDFFileObjectRef_89204c8a-3847-4e03-bf8b-c660b1b2408b.xml, umdf.iwdffile2_retrievecountedfilename, wdf.iwdffile2_retrievecountedfilename, wudfddi/IWDFFile2::RetrieveCountedFileName
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
req.lib: 
req.dll: WUDFx.dll
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - IWDFFile2::RetrieveCountedFileName
 - wudfddi/IWDFFile2::RetrieveCountedFileName
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFFile2::RetrieveCountedFileName
---

# IWDFFile2::RetrieveCountedFileName


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveCountedFileName</b> method retrieves the full counted file name for a file that is associated with a device.

## -parameters

### -param pCountedFileName 

[out]
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

A counted file name is a string that can include embedded <b>NULL</b> ('\0') characters in addition to a terminating <b>NULL</b>. To obtain a name string without embedded <b>NULL</b> characters, drivers can call <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdffile-retrievefilename">IWDFFile::RetrieveFileName</a>.

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

The following code example obtains the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile2">IWDFFile2</a> interface from the <a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile">IWDFFile</a> interface that a driver's <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackcreate-oncreatefile">IQueueCallbackCreate::OnCreateFile</a> callback function receives. The example calls <b>RetrieveCountedFileName</b> twice--once to obtain the file name's length and once to retrieve the file name string.


```
VOID
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
    hr = pWdfFileObject->QueryInterface(IID_PPV_ARGS(&pWdfFileObject2));
    if (!SUCCEEDED(hr))
    {
        goto Done;
    }
    //
    // Get length of counted filename.
    //
    hr = pWdfFileObject2->RetrieveCountedFileName(NULL,
                                                  &countedFileNameCch);
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
        hr = pWdfFileObject2->RetrieveCountedFileName(countedFileName, 
                                                      &countedFileNameCch);
        if (!SUCCEEDED(hr))
        {
            goto Done;
        }
    }
    ...
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdffile2">IWDFFile2</a>



<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdffile-retrievefilename">IWDFFile::RetrieveFileName</a>

