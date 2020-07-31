---
UID: NF:wudfddi.IPnpCallbackRemoteInterfaceNotification.OnRemoteInterfaceArrival
title: IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival (wudfddi.h)
description: A driver's OnRemoteInterfaceArrival event callback function informs the driver when a device interface is available.
old-location: wdf\ipnpcallbackremoteinterfacenotification_onremoteinterfacearrival.htm
tech.root: wdf
ms.assetid: 19a0eec7-1a67-42ad-86d2-20566a2c1268
ms.date: 02/26/2018
keywords: ["IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival"]
ms.keywords: IPnpCallbackRemoteInterfaceNotification interface,OnRemoteInterfaceArrival method, IPnpCallbackRemoteInterfaceNotification.OnRemoteInterfaceArrival, IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival, OnRemoteInterfaceArrival, OnRemoteInterfaceArrival method, OnRemoteInterfaceArrival method,IPnpCallbackRemoteInterfaceNotification interface, UMDFDeviceObjectRef_68b238b1-6614-4217-90ae-12ec291fa7ba.xml, umdf.ipnpcallbackremoteinterfacenotification_onremoteinterfacearrival, wdf.ipnpcallbackremoteinterfacenotification_onremoteinterfacearrival, wudfddi/IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival
f1_keywords:
 - "wudfddi/IPnpCallbackRemoteInterfaceNotification.OnRemoteInterfaceArrival"
 - "IPnpCallbackRemoteInterfaceNotification.OnRemoteInterfaceArrival"
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
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- Wudfddi.h
api_name:
- IPnpCallbackRemoteInterfaceNotification.OnRemoteInterfaceArrival
targetos: Windows
req.typenames: 
---

# IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnRemoteInterfaceArrival</b> event callback function informs the driver when a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a> is available. 


## -parameters




### -param pWdfRemoteInterfaceInit [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremoteinterfaceinitialize">IWDFRemoteInterfaceInitialize</a> interface that identifies the device interface that has arrived.


## -remarks



A UMDF-based driver can register its optional <b>OnRemoteInterfaceArrival</b> event callback function by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-registerremoteinterfacenotification">IWDFDevice2::RegisterRemoteInterfaceNotification</a>.

The driver can use methods of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremoteinterfaceinitialize">IWDFRemoteInterfaceInitialize</a> interface to determine which device interface has arrived.

Before the driver can send I/O requests to the device interface, the driver must do the following:

<ol>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createremoteinterface">IWDFDevice2::CreateRemoteInterface</a> to create a remote interface object.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createremotetarget">IWDFDevice2::CreateRemoteTarget</a> to create a remote target object.

</li>
<li>
Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-openremoteinterface">IWDFRemoteTarget::OpenRemoteInterface</a> to connect the interface object to the remote target object and open the remote target for I/O operations.

</li>
</ol>
For more information about using remote interface objects to access device interfaces, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-ipnpcallbackremoteinterfacenotification">IPnpCallbackRemoteInterfaceNotification</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createremoteinterface">IWDFDevice2::CreateRemoteInterface</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice2-createremotetarget">IWDFDevice2::CreateRemoteTarget</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nn-wudfddi-iwdfremoteinterfaceinitialize">IWDFRemoteInterfaceInitialize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfremotetarget-openremoteinterface">IWDFRemoteTarget::OpenRemoteInterface</a>
 

 

