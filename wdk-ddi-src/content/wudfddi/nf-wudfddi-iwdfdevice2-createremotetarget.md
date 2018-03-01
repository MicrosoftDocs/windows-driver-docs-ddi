---
UID: NF:wudfddi.IWDFDevice2.CreateRemoteTarget
title: IWDFDevice2::CreateRemoteTarget method
author: windows-driver-content
description: The CreateRemoteTarget method creates a remote target object that represents a remote I/O target.
old-location: wdf\iwdfdevice2_createremotetarget.htm
old-project: wdf
ms.assetid: 0b11d913-f488-4237-85e3-4469eefc0b91
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreateRemoteTarget method, CreateRemoteTarget method, IWDFDevice2 interface, CreateRemoteTarget,IWDFDevice2.CreateRemoteTarget, IWDFDevice2, IWDFDevice2 interface, CreateRemoteTarget method, IWDFDevice2::CreateRemoteTarget, UMDFDeviceObjectRef_877f2d10-92a7-4e04-b07e-683b728c691a.xml, umdf.iwdfdevice2_createremotetarget, wdf.iwdfdevice2_createremotetarget, wudfddi/IWDFDevice2::CreateRemoteTarget
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFDevice2.CreateRemoteTarget
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice2::CreateRemoteTarget method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateRemoteTarget</b> method creates a remote target object that represents a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a>.


## -syntax


````
HRESULT CreateRemoteTarget(
  [in, optional] IUnknown         *pCallbackInterface,
  [in, optional] IWDFObject       *pParentObject,
  [out]          IWDFRemoteTarget **ppRemoteTarget
);
````


## -parameters




### -param pCallbackInterface [in, optional]

A pointer to an optional, driver-supplied callback interface. The <b>IUnknown::QueryInterface</b> method of this interface must return a pointer to the driver's <a href="..\wudfddi\nn-wudfddi-iremotetargetcallbackremoval.md">IRemoteTargetCallbackRemoval</a> interface, if the driver supports that interface. This parameter is optional and can be <b>NULL</b>.


### -param pParentObject [in, optional]

A pointer to a framework object. If the driver provides this optional pointer, the specified object becomes the parent of the new remote target object. If this parameter is <b>NULL</b>, the device object that provides the <a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a> interface becomes the parent. The framework will delete the remote target object when it deletes the parent object. 


### -param ppRemoteTarget [out]

A pointer to a location that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfremotetarget.md">IWDFRemoteTarget</a> interface of the new remote target object.


## -returns



<b>CreateRemoteTarget</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:

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
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_INVALID_PARAMETER)</b></dt>
</dl>
</td>
<td width="60%">
The <i>pParentObject</i> parameter did not specify the device object that provides the <a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a> interface or an object whose chain of parents leads to that object. 

</td>
</tr>
</table>
 

This method might return one of the other values that Winerror.h contains.




## -remarks



After your driver has called <b>CreateRemoteTarget</b>, the driver can open the remote target by calling either <a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a> (to open a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>) or <a href="https://msdn.microsoft.com/library/windows/hardware/ff560273">IWDFRemoteTarget::OpenFileByName</a> (to open a file).

If the driver uses the <i>pParentObject</i> parameter to specify a parent object, the parent object can be the device object that provides the <a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a> interface, or it can be any object whose chain of parents leads to that device object. The framework will delete the remote target object when it (or the driver) deletes the device object.

For more information about remote I/O targets, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-i-o-targets-in-umdf">Using I/O Targets in UMDF</a>.


#### Examples

For code examples that use <b>CreateRemoteTarget</b>, see the code examples at <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff560273">IWDFRemoteTarget::OpenFileByName</a>.

<div class="code"></div>



## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560273">IWDFRemoteTarget::OpenFileByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice2::CreateRemoteTarget method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

