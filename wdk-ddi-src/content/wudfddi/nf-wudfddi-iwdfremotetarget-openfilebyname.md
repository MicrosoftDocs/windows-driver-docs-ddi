---
UID: NF:wudfddi.IWDFRemoteTarget.OpenFileByName
title: IWDFRemoteTarget::OpenFileByName (wudfddi.h)
description: The OpenFileByName method opens a remote I/O target that is a file.
old-location: wdf\iwdfremotetarget_openfilebyname.htm
tech.root: wdf
ms.assetid: 7f0cef78-3edc-434b-af70-39694776e8a7
ms.date: 02/26/2018
ms.keywords: IWDFRemoteTarget interface,OpenFileByName method, IWDFRemoteTarget.OpenFileByName, IWDFRemoteTarget::OpenFileByName, OpenFileByName, OpenFileByName method, OpenFileByName method,IWDFRemoteTarget interface, UMDFIoTargetObjectRef_909b78ee-2d3a-46b2-bfca-f72063ca62f8.xml, umdf.iwdfremotetarget_openfilebyname, wdf.iwdfremotetarget_openfilebyname, wudfddi/IWDFRemoteTarget::OpenFileByName
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
- IWDFRemoteTarget.OpenFileByName
product:
- Windows
targetos: Windows
req.typenames: 
---

# IWDFRemoteTarget::OpenFileByName


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OpenFileByName</b> method opens a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a> that is a file.


## -parameters




### -param pszFileName [in]

A pointer to a caller-supplied, <b>null</b>-terminated string that represents the name of the file to open. For more information about this member, see the <i>FileName</i> parameter of <a href="https://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a> in the Windows SDK.


### -param DesiredAccess [in]

A bitmask that specifies the caller's desired access to the file. For more information about this member, see the <i>dwDesiredAccess</i> parameter of <a href="https://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a> in the Windows SDK.


### -param pOpenParams [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff561275">UMDF_IO_TARGET_OPEN_PARAMS</a> structure that contains additional parameters. This parameter is optional and can be <b>NULL</b>.


## -returns



<b>OpenFileByName</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:

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
The framework's attempt to allocate memory failed. 

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.



The framework's <a href="https://msdn.microsoft.com/e84993e1-da10-4041-8fc7-7f40806ee454">verifier</a> reports an error if the framework cannot open the file.




## -remarks



Your driver can use <b>OpenFileByName</b> to open a file, if the driver stack to which your driver belongs does not support the file's device. Use <a href="https://msdn.microsoft.com/library/windows/hardware/ff558930">IWDFFileHandleTargetFactory::CreateFileHandleTarget</a> to open a file, if the driver stack to which your driver belongs does support the file's device.

The specified file must be accessible by the account that loaded the UMDF-based driver, which is typically the Local Service account. However, if the driver uses <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">impersonation</a> when it calls <b>OpenFileByName</b>, the file must be accessible by the impersonated account.

Do not call <b>OpenFileByName</b> to open a remote target to a control device object. Instead, open the control device directly by calling <a href="https://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a>.

For more information about the <b>OpenFileByName</b> method and remote I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">General I/O Targets in UMDF</a>.


#### Examples

The following code example creates a remote target object and opens an existing file with read-only access.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>UMDF_IO_TARGET_OPEN_PARAMS openParams;
HRESULT hr;

//
// Create a new remote target object and provide a callback 
// object to handle remote target events.
//
CComPtr&lt;IWDFRemoteTarget&gt; fxTarget;
hr = FxDevice-&gt;CreateRemoteTarget(MyRemoteTargetIUnknown,
                                  fxRemoteInterface,
                                  &fxTarget);
if (FAILED(hr)) goto Error;

//
// Open existing file for read-only access.
//
openParams.dwShareMode = 0;
openParams.dwCreationDisposition = OPEN_EXISTING;
openParams.dwFlagsAndAttributes = FILE_ATTRIBUTE_READONLY;

hr = fxTarget-&gt;OpenFileByName(FILE_PATH,
                              GENERIC_READ,
                              &openParams);
 </pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556928">IWDFDevice2::CreateRemoteTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560247">IWDFRemoteTarget</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a>
 

 

