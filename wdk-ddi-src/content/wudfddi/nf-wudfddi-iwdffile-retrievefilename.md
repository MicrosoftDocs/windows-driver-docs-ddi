---
UID: NF:wudfddi.IWDFFile.RetrieveFileName
title: IWDFFile::RetrieveFileName (wudfddi.h)
description: The RetrieveFileName method retrieves the full name of the file that is associated with the underlying kernel-mode device.
old-location: wdf\iwdffile_retrievefilename.htm
tech.root: wdf
ms.assetid: 7858f3ba-e02a-4115-bf30-12e3a6a75965
ms.date: 02/26/2018
ms.keywords: IWDFFile interface,RetrieveFileName method, IWDFFile.RetrieveFileName, IWDFFile::RetrieveFileName, RetrieveFileName, RetrieveFileName method, RetrieveFileName method,IWDFFile interface, UMDFFileObjectRef_6c460bef-f774-4f9c-9e56-3c57ad023ae8.xml, umdf.iwdffile_retrievefilename, wdf.iwdffile_retrievefilename, wudfddi/IWDFFile::RetrieveFileName
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
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- WUDFx.dll
api_name:
- IWDFFile.RetrieveFileName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFFile::RetrieveFileName


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveFileName</b> method retrieves the full name of the file that is associated with the underlying kernel-mode device.


## -parameters




### -param pFileName [out]

A pointer to a caller-supplied buffer that receives a <b>NULL</b>-terminated string that represents the full name of the file that is associated with the underlying kernel-mode device, if the supplied pointer is non-<b>NULL</b> and <b>RetrieveFileName</b> is successful. 


### -param pdwFileNameLengthInChars [in, out]

A pointer to a caller-supplied variable that receives the size, in characters, of the full file name that <i>pFileName</i> points to. If the buffer at <i>pFileName</i> is non-<b>NULL</b>, the framework returns the size, in characters, of the file name string.

On input, the driver sets this variable to the size, in characters, of the buffer that <i>pFileName</i> points to. If the driver supplies <b>NULL</b> for <i>pFileName</i> and zero for the variable that <i>pdwFileNameLengthInChars</i> points to, the framework sets the variable to the size, in characters, that the file name string requires.


## -returns



<b>RetrieveFileName</b> returns S_OK for the following scenarios:


<ul>
<li>
The buffer that the <i>pFileName</i> parameter points to was non-<b>NULL</b> and large enough to hold the name string, including the <b>NULL</b> character, and the framework successfully copied the string into the supplied buffer and set the variable that is pointed to by the <i>pdwFileNameLengthInChars</i> parameter to the number of characters in the string.

</li>
<li>
The buffer at <i>pFileName</i> was <b>NULL</b>, the driver preset the variable at <i>pdwFileNameLengthInChars</i> to 0, and the framework set the variable at <i>pdwFileNameLengthInChars</i> to the number of characters that are required for the string. 


</li>
</ul><b>RetrieveFileName</b> returns HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER) to indicate that the supplied buffer is non-<b>NULL</b> and did not contain enough space to hold the file name. The framework sets the variable at <i>pdwFileNameLengthInChars</i> to the number of characters that are required for the string.



<b>RetrieveFileName</b> might also return other HRESULT values.




## -remarks



Your driver might call <b>RetrieveFileName</b> from its <a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a> callback function.  For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF Drivers</a>.


#### Examples

The following code example shows how to retrieve the name of a file.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>    ULONG fileNameCch = 0;
    PWSTR fileName = NULL;
    ULONG index;

    CComObject&lt;CUmdfHidFile&gt; *file = NULL;

    HRESULT hr;

    // Get the length of the file name to allocate a buffer.
    hr = WdfFile-&gt;RetrieveFileName(NULL, &amp;fileNameCch);
    //
    // Allocate the buffer.
    //
    if (SUCCEEDED(hr))
    {
        fileName = new WCHAR[fileNameCch];

        if (fileName == NULL)
        {
            hr = E_OUTOFMEMORY;
        }
    }
    //
    // Get the file name.
    //
    if (SUCCEEDED(hr))
    {
        hr = WdfFile-&gt;RetrieveFileName(fileName, &amp;fileNameCch);
    }</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a>
 

 

