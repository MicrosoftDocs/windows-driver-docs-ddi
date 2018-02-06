---
UID: NF:wudfddi.IWDFDevice2.CreateRemoteInterface
title: IWDFDevice2::CreateRemoteInterface method
author: windows-driver-content
description: The CreateRemoteInterface method creates a remote interface object that represents a device interface.
old-location: wdf\iwdfdevice2_createremoteinterface.htm
old-project: wdf
ms.assetid: fb2def4b-c027-465d-b734-20b4b83a6308
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFDevice2 interface, CreateRemoteInterface method, wudfddi/IWDFDevice2::CreateRemoteInterface, IWDFDevice2::CreateRemoteInterface, CreateRemoteInterface, UMDFDeviceObjectRef_772989d9-ec18-4672-abea-ee4abd00b6ee.xml, CreateRemoteInterface method, umdf.iwdfdevice2_createremoteinterface, wdf.iwdfdevice2_createremoteinterface, CreateRemoteInterface method, IWDFDevice2 interface, IWDFDevice2
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
-	IWDFDevice2.CreateRemoteInterface
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IWDFDevice2::CreateRemoteInterface method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CreateRemoteInterface</b> method creates a remote interface object that represents a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>.


## -syntax


````
HRESULT CreateRemoteInterface(
  [in]           IWDFRemoteInterfaceInitialize *pRemoteInterfaceInit,
  [in, optional] IUnknown                      *pCallbackInterface,
  [out]          IWDFRemoteInterface           **ppRemoteInterface
);
````


## -parameters




### -param pRemoteInterfaceInit [in]

A pointer to an <a href="..\wudfddi\nn-wudfddi-iwdfremoteinterfaceinitialize.md">IWDFRemoteInterfaceInitialize</a> interface that the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556775">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function received.


### -param pCallbackInterface [in, optional]

A pointer to an optional, driver-supplied callback interface. The <b>IUnknown::QueryInterface</b> method of this interface must return a pointer to the driver's <a href="..\wudfddi\nn-wudfddi-iremoteinterfacecallbackevent.md">IRemoteInterfaceCallbackEvent</a> and <a href="..\wudfddi\nn-wudfddi-iremoteinterfacecallbackremoval.md">IRemoteInterfaceCallbackRemoval</a> interfaces, if the driver supports those interfaces. This parameter is optional and can be <b>NULL</b>.


### -param ppRemoteInterface [out]

A pointer to a driver-supplied location that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfremoteinterface.md">IWDFRemoteInterface</a> interface of the new remote interface object.


## -returns


<b>CreateRemoteInterface</b> returns S_OK if the operation succeeds. Otherwise, the method might return the following value:
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



## -remarks


If your driver calls <b>CreateRemoteInterface</b>, it must do so from within its <a href="https://msdn.microsoft.com/library/windows/hardware/ff556775">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a> callback function.

For more information about <b>CreateRemoteInterface</b> and using device interfaces, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>




## -see-also

<a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556928">IWDFDevice2::CreateRemoteTarget</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice2::CreateRemoteInterface method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

