---
UID: NF:wudfddi.IWDFIoRequest2.GetCreateParametersEx
title: IWDFIoRequest2::GetCreateParametersEx (wudfddi.h)
description: The GetCreateParametersEx method retrieves file creation parameters that are associated with a file that is being created or opened.
old-location: wdf\iwdfiorequest2_getcreateparametersex.htm
tech.root: wdf
ms.assetid: bc34d86b-fa0e-419e-9342-61df12a8e484
ms.date: 02/26/2018
keywords: ["IWDFIoRequest2::GetCreateParametersEx"]
ms.keywords: GetCreateParametersEx, GetCreateParametersEx method, GetCreateParametersEx method,IWDFIoRequest2 interface, IWDFIoRequest2 interface,GetCreateParametersEx method, IWDFIoRequest2.GetCreateParametersEx, IWDFIoRequest2::GetCreateParametersEx, UMDFRequestObjectRef_02864469-8022-4412-8de9-639dcd0b4f42.xml, umdf.iwdfiorequest2_getcreateparametersex, wdf.iwdfiorequest2_getcreateparametersex, wudfddi/IWDFIoRequest2::GetCreateParametersEx
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
 - IWDFIoRequest2::GetCreateParametersEx
 - wudfddi/IWDFIoRequest2::GetCreateParametersEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - WUDFx.dll
api_name:
 - IWDFIoRequest2.GetCreateParametersEx
---

# IWDFIoRequest2::GetCreateParametersEx


## -description

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCreateParametersEx</b> method retrieves file creation parameters that are associated with a file that is being created or opened.

## -parameters

### -param pOptions 

[out, optional]
A pointer to a caller-allocated variable that receives bit flags that indicate file creation options. These FILE_XXXX-named bit flags are defined in Wdm.h. 

The low 24 bits of the variable indicate options to apply when creating or opening the file. For more information about these bits, see the description of the <i>CreateOptions</i> parameter of the kernel-mode <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a> function. 

The high eight bits of the variable indicate actions to perform if the file does or does not already exist. For more information about these bits, see the description of the <i>CreateDisposition</i> parameter of <b>ZwCreateFile</b>. 

This parameter is optional and can be <b>NULL</b>.

### -param pFileAttributes 

[out, optional]
A pointer to a caller-allocated variable that receives bit flags that indicate file attributes. These FILE_ATTRIBUTE_XXXX-named bit flags are defined in Wdm.h. For more information about these bit flags, see the description of the <i>FileAttributes</i> parameter of <b>ZwCreateFile</b>.

This parameter is optional and can be <b>NULL</b>.

### -param pShareAccess 

[out, optional]
A pointer to a caller-allocated variable that receives bit flags that indicate file sharing options. These FILE_SHARE_XXXX-named bit flags are defined in Wdm.h. For more information about these bit flags, see the description of the <i>ShareAccess</i> parameter of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ntcreatefile">ZwCreateFile</a>.

This parameter is optional and can be <b>NULL</b>.

### -param pDesiredAccess 

[out, optional]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> structure that specifies the requested access to the file. For more information about this parameter, see the <i>DesiredAccess</i> parameter of <b>ZwCreateFile</b>. 

This parameter is optional and can be <b>NULL</b>.

## -remarks

After the framework calls a driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackcreate-oncreatefile">IQueueCallbackCreate::OnCreateFile</a> callback function, the driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getcreateparameters">IWDFIoRequest::GetCreateParameters</a> method or the <b>IWDFIoRequest2::GetCreateParametersEx</b> method to obtain the file's creation parameters. 

For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/obtaining-parameters-for-i-o-requests">Obtaining Parameters for I/O Requests</a>.


#### Examples

The following code example shows how an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackcreate-oncreatefile">IQueueCallbackCreate::OnCreateFile</a> callback function can obtain the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a> interface and then call <b>GetCreateParametersEx</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
OnCreateFile(
    __in IWDFIoQueue* FxQueue,
    __in IWDFIoRequest* FxRequest,
    __in IWDFFile* FxFile
    )
{
    ULONG fileOptions;
    USHORT fileAttributes,
    USHORT shareAccess,
    ACCESS_MASK desiredAccess;
    ...
    CComQIPtr<IWDFIoRequest2> fxRequest2(FxRequest);
    fxRequest2->GetCreateParametersEx(&fileOptions
                                      &fileAttributes,
                                      &shareAccess,
                                      &desiredAccess);
    ...
}</pre>
</td>
</tr>
</table></span></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iqueuecallbackcreate-oncreatefile">IQueueCallbackCreate::OnCreateFile</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfiorequest2">IWDFIoRequest2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfiorequest-getcreateparameters">IWDFIoRequest::GetCreateParameters</a>

