---
UID: NF:wudfddi.IWDFIoRequest2.GetCreateParametersEx
title: IWDFIoRequest2::GetCreateParametersEx method
author: windows-driver-content
description: The GetCreateParametersEx method retrieves file creation parameters that are associated with a file that is being created or opened.
old-location: wdf\iwdfiorequest2_getcreateparametersex.htm
old-project: wdf
ms.assetid: bc34d86b-fa0e-419e-9342-61df12a8e484
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: IWDFIoRequest2 interface, GetCreateParametersEx method, IWDFIoRequest2, GetCreateParametersEx method, GetCreateParametersEx, wudfddi/IWDFIoRequest2::GetCreateParametersEx, wdf.iwdfiorequest2_getcreateparametersex, IWDFIoRequest2::GetCreateParametersEx, umdf.iwdfiorequest2_getcreateparametersex, GetCreateParametersEx method, IWDFIoRequest2 interface, UMDFRequestObjectRef_02864469-8022-4412-8de9-639dcd0b4f42.xml
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
-	IWDFIoRequest2.GetCreateParametersEx
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoRequest2::GetCreateParametersEx method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>GetCreateParametersEx</b> method retrieves file creation parameters that are associated with a file that is being created or opened.


## -syntax


````
void GetCreateParametersEx(
  [out, optional] ULONG       *pOptions,
  [out, optional] USHORT      *pFileAttributes,
  [out, optional] USHORT      *pShareAccess,
  [out, optional] ACCESS_MASK *pDesiredAccess
);
````


## -parameters




### -param pOptions [out, optional]

A pointer to a caller-allocated variable that receives bit flags that indicate file creation options. These FILE_XXXX-named bit flags are defined in Wdm.h. 

The low 24 bits of the variable indicate options to apply when creating or opening the file. For more information about these bits, see the description of the <i>CreateOptions</i> parameter of the kernel-mode <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a> function. 

The high eight bits of the variable indicate actions to perform if the file does or does not already exist. For more information about these bits, see the description of the <i>CreateDisposition</i> parameter of <b>ZwCreateFile</b>. 

This parameter is optional and can be <b>NULL</b>.


### -param pFileAttributes [out, optional]

A pointer to a caller-allocated variable that receives bit flags that indicate file attributes. These FILE_ATTRIBUTE_XXXX-named bit flags are defined in Wdm.h. For more information about these bit flags, see the description of the <i>FileAttributes</i> parameter of <b>ZwCreateFile</b>.

This parameter is optional and can be <b>NULL</b>.


### -param pShareAccess [out, optional]

A pointer to a caller-allocated variable that receives bit flags that indicate file sharing options. These FILE_SHARE_XXXX-named bit flags are defined in Wdm.h. For more information about these bit flags, see the description of the <i>ShareAccess</i> parameter of <a href="..\wdm\nf-wdm-zwcreatefile.md">ZwCreateFile</a>.

This parameter is optional and can be <b>NULL</b>.


### -param pDesiredAccess [out, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> structure that specifies the requested access to the file. For more information about this parameter, see the <i>DesiredAccess</i> parameter of <b>ZwCreateFile</b>. 

This parameter is optional and can be <b>NULL</b>.


## -returns



None.




## -remarks



After the framework calls a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a> callback function, the driver can call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559088">IWDFIoRequest::GetCreateParameters</a> method or the <b>IWDFIoRequest2::GetCreateParametersEx</b> method to obtain the file's creation parameters. 

For more information, see <a href="https://msdn.microsoft.com/1ba1fdcf-99bd-44e3-adbf-5dc93a790900">Obtaining Parameters for I/O Requests</a>.


#### Examples

The following code example shows how an <a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a> callback function can obtain the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a> interface and then call <b>GetCreateParametersEx</b>.

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
    CComQIPtr&lt;IWDFIoRequest2&gt; fxRequest2(FxRequest);
    fxRequest2-&gt;GetCreateParametersEx(&amp;fileOptions
                                      &amp;fileAttributes,
                                      &amp;shareAccess,
                                      &amp;desiredAccess);
    ...
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559088">IWDFIoRequest::GetCreateParameters</a>



<a href="..\wudfddi\nn-wudfddi-iwdfiorequest2.md">IWDFIoRequest2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest2::GetCreateParametersEx method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

