---
UID: NF:wudfddi.IPnpCallbackRemoteInterfaceNotification.OnRemoteInterfaceArrival
title: IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival method
author: windows-driver-content
description: A driver's OnRemoteInterfaceArrival event callback function informs the driver when a device interface is available.
old-location: wdf\ipnpcallbackremoteinterfacenotification_onremoteinterfacearrival.htm
old-project: wdf
ms.assetid: 19a0eec7-1a67-42ad-86d2-20566a2c1268
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IPnpCallbackRemoteInterfaceNotification, IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival, umdf.ipnpcallbackremoteinterfacenotification_onremoteinterfacearrival, IPnpCallbackRemoteInterfaceNotification interface, OnRemoteInterfaceArrival method, wudfddi/IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival, wdf.ipnpcallbackremoteinterfacenotification_onremoteinterfacearrival, OnRemoteInterfaceArrival method, OnRemoteInterfaceArrival, UMDFDeviceObjectRef_68b238b1-6614-4217-90ae-12ec291fa7ba.xml, OnRemoteInterfaceArrival method, IPnpCallbackRemoteInterfaceNotification interface
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
-	IPnpCallbackRemoteInterfaceNotification.OnRemoteInterfaceArrival
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnRemoteInterfaceArrival</b> event callback function informs the driver when a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a> is available. 


## -syntax


````
void OnRemoteInterfaceArrival(
  [in] IWDFRemoteInterfaceInitialize *pWdfRemoteInterfaceInit
);
````


## -parameters




### -param pWdfRemoteInterfaceInit [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfremoteinterfaceinitialize.md">IWDFRemoteInterfaceInitialize</a> interface that identifies the device interface that has arrived.


## -returns


None.



## -remarks


A UMDF-based driver can register its optional <b>OnRemoteInterfaceArrival</b> event callback function by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff556939">IWDFDevice2::RegisterRemoteInterfaceNotification</a>.

The driver can use methods of the <a href="..\wudfddi\nn-wudfddi-iwdfremoteinterfaceinitialize.md">IWDFRemoteInterfaceInitialize</a> interface to determine which device interface has arrived.

Before the driver can send I/O requests to the device interface, the driver must do the following:
<ol>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a> to create a remote interface object.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff556928">IWDFDevice2::CreateRemoteTarget</a> to create a remote target object.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a> to connect the interface object to the remote target object and open the remote target for I/O operations.

</li>
</ol>For more information about using remote interface objects to access device interfaces, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a>

<a href="..\wudfddi\nn-wudfddi-iwdfremoteinterfaceinitialize.md">IWDFRemoteInterfaceInitialize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a>

<a href="..\wudfddi\nn-wudfddi-ipnpcallbackremoteinterfacenotification.md">IPnpCallbackRemoteInterfaceNotification</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556928">IWDFDevice2::CreateRemoteTarget</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

