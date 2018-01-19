---
UID: NF:wudfddi.IWDFRemoteInterfaceInitialize.RetrieveSymbolicLink
title: IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink method
author: windows-driver-content
description: The RetrieveSymbolicLink method retrieves the symbolic link name that the operating system assigned to a device interface.
old-location: wdf\iwdfremoteinterfaceinitialize_retrievesymboliclink.htm
old-project: wdf
ms.assetid: e3203542-177c-440a-8d41-4d70d77f804d
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFRemoteInterfaceInitialize, IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink, RetrieveSymbolicLink
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
req.alt-api: IWDFRemoteInterfaceInitialize.RetrieveSymbolicLink
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

# IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveSymbolicLink</b> method retrieves the symbolic link name that the operating system assigned to a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>. 



## -syntax

````
HRESULT RetrieveSymbolicLink(
  [out, optional] PWSTR pSymbolicLink,
  [in, out]       DWORD *pdwSymbolicLinkLengthInChars
);
````


## -parameters

### -param pSymbolicLink [out, optional]

A pointer to a buffer that receives a <b>null</b>-terminated Unicode character string that represents the symbolic link name. Set this pointer to <b>NULL</b> to obtain the required buffer size.


### -param pdwSymbolicLinkLengthInChars [in, out]

A pointer to a caller-allocated location. On input, this location must contain the caller-supplied length of the buffer that <i>pSymbolicLink</i> points to. On output, the location receives the length, in characters, of the symbolic link name, including the <b>NULL</b> terminating character.


## -returns
<b>RetrieveSymbolicLink</b> returns S_OK if the operation succeeds. Otherwise the method might return the following value:
<dl>
<dt><b>E_NOT_SUFFICIENT_BUFFER</b></dt>
</dl>The buffer that <i>pSymbolicLink</i> points to is too small. In this case, the framework stores the required buffer size in the location that <i>pdwSymbolicLinkLengthInChars</i> points to.

 

This method might return one of the other values that Winerror.h contains.


## -remarks
The symbolic link name can include an appended backslash (\) character, followed by an instance-specific reference string.

Typically, your driver should call <b>RetrieveSymbolicLink</b> twice, as follows:

Set the <i>pSymbolicLink</i> parameter to <b>NULL</b> and call <b>RetrieveSymbolicLink</b>. The location that <i>pdwSymbolicLinkLengthInChars</i> points to receives the number of characters that the symbolic link name contains.

Allocate a buffer that is large enough to receive the symbolic link name.

Call <b>RetrieveSymbolicLink</b> again, and set the <i>pSymbolicLink</i> parameter to the address of the buffer that you allocated.

For more information about the <b>RetrieveSymbolicLink</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>.

The following code example shows how a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556775">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function can determine the length of device interface's symbolic link name, allocate a buffer for the name, and then retrieve the name.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfremoteinterfaceinitialize.md">IWDFRemoteInterfaceInitialize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560238">IWDFRemoteInterfaceInitialize::GetInterfaceGuid</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRemoteInterfaceInitialize::RetrieveSymbolicLink method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

