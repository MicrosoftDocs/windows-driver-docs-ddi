---
UID: NF:wudfddi.IWDFRemoteTarget.OpenRemoteInterface
title: IWDFRemoteTarget::OpenRemoteInterface method
author: windows-driver-content
description: The OpenRemoteInterface method opens a device interface so that the driver can send I/O requests to it.
old-location: wdf\iwdfremotetarget_openremoteinterface.htm
old-project: wdf
ms.assetid: 5d278cde-3ebe-4fee-86fd-1ec4e79bd837
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: OpenRemoteInterface, OpenRemoteInterface method, IWDFRemoteTarget, OpenRemoteInterface method, IWDFRemoteTarget interface, wudfddi/IWDFRemoteTarget::OpenRemoteInterface, umdf.iwdfremotetarget_openremoteinterface, wdf.iwdfremotetarget_openremoteinterface, IWDFRemoteTarget interface, OpenRemoteInterface method, UMDFIoTargetObjectRef_e8287a4e-9f63-40e6-9a85-fb881a27d292.xml, IWDFRemoteTarget::OpenRemoteInterface
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
-	IWDFRemoteTarget.OpenRemoteInterface
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFRemoteTarget::OpenRemoteInterface method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OpenRemoteInterface</b> method opens a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a> so that the driver can send I/O requests to it.


## -syntax


````
HRESULT OpenRemoteInterface(
  [in]           IWDFRemoteInterface         *pRemoteInterface,
  [in, optional] PCWSTR                      pszRelativeFileName,
  [in]           DWORD                       DesiredAccess,
  [in, optional] PUMDF_IO_TARGET_OPEN_PARAMS pOpenParams
);
````


## -parameters




### -param pRemoteInterface [in]

A pointer to a <a href="..\wudfddi\nn-wudfddi-iwdfremoteinterface.md">IWDFRemoteInterface</a> interface that the driver obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a>.


### -param pszRelativeFileName [in, optional]

An optional pointer to a caller-supplied, <b>null</b>-terminated string that the framework appends to the symbolic link name of the device interface. 


### -param DesiredAccess [in]

A bitmask that specifies the caller's desired access to the file. For more information about this member, see the <i>DesiredAccess</i> parameter of <a href="http://go.microsoft.com/fwlink/p/?linkid=152795">CreateFile</a> in the Windows SDK.


### -param pOpenParams [in, optional]

A pointer to a caller-allocated <a href="..\wudfddi\ns-wudfddi-_umdf_io_target_open_params.md">UMDF_IO_TARGET_OPEN_PARAMS</a> structure that contains additional parameters. This parameter is optional and can be <b>NULL</b>.


## -returns


<b>OpenRemoteInterface</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:
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


After a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556775">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function receives notification that a device interface is available, and after the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a> to create a remote interface object, the driver can call <b>OpenRemoteInterface</b> so that it can send I/O requests to the device interface.

The device interface must be accessible by the account that loaded the UMDF-based driver, which is typically the Local Service account. However, if the driver uses <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/handling-client-impersonation-in-umdf-drivers">impersonation</a> when it calls <b>OpenRemoteInterface</b>, the device interface must be accessible by the impersonated account.

For more information about <b>OpenRemoteInterface</b> and how to use device interfaces in UMDF-based drivers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>.



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfremotetarget.md">IWDFRemoteTarget</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560273">IWDFRemoteTarget::OpenFileByName</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFRemoteTarget::OpenRemoteInterface method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

