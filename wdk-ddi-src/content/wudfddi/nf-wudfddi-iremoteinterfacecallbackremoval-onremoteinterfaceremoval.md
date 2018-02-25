---
UID: NF:wudfddi.IRemoteInterfaceCallbackRemoval.OnRemoteInterfaceRemoval
title: IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval method
author: windows-driver-content
description: A UMDF-based driver's OnRemoteInterfaceRemoval event callback function notifies the driver that it cannot use a device interface because the interface has been removed.
old-location: wdf\iremoteinterfacecallbackremoval_onremoteinterfaceremoval.htm
old-project: wdf
ms.assetid: 0dfa2eb8-a7f6-46d9-9599-5e2aaf583f78
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , ,, ., :, C, I, IRemoteInterfaceCallbackRemoval, IRemoteInterfaceCallbackRemoval interface, OnRemoteInterfaceRemoval method, IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval, O, OnRemoteInterfaceRemoval method, OnRemoteInterfaceRemoval method, IRemoteInterfaceCallbackRemoval interface, OnRemoteInterfaceRemoval,IRemoteInterfaceCallbackRemoval.OnRemoteInterfaceRemoval, R, UMDFIoTargetObjectRef_17c1557c-2046-4bea-8b7f-88fea7103155.xml, a, b, c, e, f, k, l, m, n, o, r, t, umdf.iremoteinterfacecallbackremoval_onremoteinterfaceremoval, v, wdf.iremoteinterfacecallbackremoval_onremoteinterfaceremoval, wudfddi/IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval"
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
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wudfddi.h
apiname:
-	IRemoteInterfaceCallbackRemoval.OnRemoteInterfaceRemoval
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A UMDF-based driver's <b>OnRemoteInterfaceRemoval</b> event callback function notifies the driver that it cannot use a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a> because the interface has been removed.


## -syntax


````
void OnRemoteInterfaceRemoval(
  [in] IWDFRemoteInterface *pWdfRemoteInterface
);
````


## -parameters




### -param pWdfRemoteInterface [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfremoteinterface.md">IWDFRemoteInterface</a> interface of a remote interface object that represents a device interface. The driver obtains this pointer when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a>.


## -returns



None.




## -remarks



A driver's <b>OnRemoteInterfaceRemoval</b> event callback function must do whatever driver-specific tasks are necessary to handle removal of the device interface. In addition, the callback must delete the remote interface object that <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a> created and call the interface's <b>Release</b> function if it has previously called the interface's <b>AddRef</b> function.

If the driver does not provide this callback function, the framework deletes the remote interface object that <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a> created. 

For more information about a driver's <b>OnRemoteInterfaceRemoval</b> event callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556775">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556889">IRemoteInterfaceCallbackEvent::OnRemoteInterfaceEvent</a>



<a href="..\wudfddi\nn-wudfddi-iremoteinterfacecallbackremoval.md">IRemoteInterfaceCallbackRemoval</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

