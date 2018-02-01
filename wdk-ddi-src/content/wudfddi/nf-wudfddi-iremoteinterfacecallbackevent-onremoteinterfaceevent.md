---
UID: NF:wudfddi.IRemoteInterfaceCallbackEvent.OnRemoteInterfaceEvent
title: IRemoteInterfaceCallbackEvent::OnRemoteInterfaceEvent method
author: windows-driver-content
description: A UMDF-based driver's OnRemoteInterfaceEvent event callback function handles device events that are associated with a device interface.
old-location: wdf\iremoteinterfacecallbackevent_onremoteinterfaceevent.htm
old-project: wdf
ms.assetid: 6cee6662-2eef-4caf-ab70-780748521ba9
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IRemoteInterfaceCallbackEvent, IRemoteInterfaceCallbackEvent::OnRemoteInterfaceEvent, OnRemoteInterfaceEvent, wudfddi/IRemoteInterfaceCallbackEvent::OnRemoteInterfaceEvent, UMDFIoTargetObjectRef_4adfa540-b8f4-416f-b8c2-f0aec6e87619.xml, umdf.iremoteinterfacecallbackevent_onremoteinterfaceevent, wdf.iremoteinterfacecallbackevent_onremoteinterfaceevent, IRemoteInterfaceCallbackEvent interface, OnRemoteInterfaceEvent method, OnRemoteInterfaceEvent method, IRemoteInterfaceCallbackEvent interface, OnRemoteInterfaceEvent method
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
-	IRemoteInterfaceCallbackEvent.OnRemoteInterfaceEvent
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IRemoteInterfaceCallbackEvent::OnRemoteInterfaceEvent method


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A UMDF-based driver's <b>OnRemoteInterfaceEvent</b> event callback function handles device events that are associated with a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">device interface</a>.


## -syntax


````
void OnRemoteInterfaceEvent(
  [in]           IWDFRemoteInterface *pWdfRemoteInterface,
  [in]           REFGUID             EventGuid,
  [in, optional] BYTE                *pbData,
  [in]           DWORD               cbDataSize,
  [in]           DWORD               NameBufferOffset
);
````


## -parameters




### -param pWdfRemoteInterface [in]

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfremoteinterface.md">IWDFRemoteInterface</a> interface of a remote interface object that represents a device interface. The driver obtains this pointer when it calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff556925">IWDFDevice2::CreateRemoteInterface</a>.


### -param EventGuid [in]

A GUID that identifies the event type. Event GUIDs are defined by the components that support such GUIDs. Some <a href="https://msdn.microsoft.com/C989D2D3-E8DE-4D64-86EE-3D3B3906390D">device interface classes</a> provide event GUIDs, and some driver provide custom events.


### -param pbData [in, optional]

A pointer to a buffer that contains event-specific data. Typically, components that define event GUIDs also define event-specific structures for event buffers.


### -param cbDataSize [in]

The size, in bytes, of the buffer that <i>pbData</i> points to.


### -param NameBufferOffset [in]

An offset, in bytes, from the beginning of the buffer that <i>pbData</i> points to. Bytes from 0 to <i>NameBufferOffset</i>-1 of the buffer contain binary data. Bytes from <i>NameBufferOffset</i> to the end of the buffer contain Unicode string data. 


## -returns


None.



## -remarks


A driver's <b>OnRemoteInterfaceEvent</b> event callback function handles all device events except arrival and removal events. Such events can originate from a UMDF-based driver's call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff558835">IWDFDevice::PostEvent</a> or from a kernel-mode driver's call to <a href="..\wdm\nf-wdm-ioreporttargetdevicechange.md">IoReportTargetDeviceChange</a> or <a href="..\wdm\nf-wdm-ioreporttargetdevicechangeasynchronous.md">IoReportTargetDeviceChangeAsynchronous</a>.

The framework begins calling the <b>OnRemoteInterfaceEvent</b> event callback function after the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff560276">IWDFRemoteTarget::OpenRemoteInterface</a> and continues to call the callback function until the device interface's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/general-i-o-targets-in-umdf">remote I/O target</a> is closed.

For more information about a driver's <b>OnRemoteInterfaceEvent</b> event callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-device-interfaces-in-umdf-drivers">Using Device Interfaces in UMDF-based Drivers</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556775">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556893">IRemoteInterfaceCallbackRemoval::OnRemoteInterfaceRemoval</a>

<a href="..\wudfddi\nn-wudfddi-iremoteinterfacecallbackevent.md">IRemoteInterfaceCallbackEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IRemoteInterfaceCallbackEvent::OnRemoteInterfaceEvent method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

