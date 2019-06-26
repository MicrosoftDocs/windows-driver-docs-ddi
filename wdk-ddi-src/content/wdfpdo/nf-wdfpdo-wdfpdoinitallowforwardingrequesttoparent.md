---
UID: NF:wdfpdo.WdfPdoInitAllowForwardingRequestToParent
title: WdfPdoInitAllowForwardingRequestToParent function (wdfpdo.h)
description: The WdfPdoInitAllowForwardingRequestToParent method enables a driver's ability to call WdfRequestForwardToParentDeviceIoQueue.
old-location: wdf\wdfpdoinitallowforwardingrequesttoparent.htm
tech.root: wdf
ms.assetid: fc8e4484-4059-4274-bb61-5d3b2f965b19
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_1c47c0f6-2474-419b-8a6e-1105351ab1d7.xml, WdfPdoInitAllowForwardingRequestToParent, WdfPdoInitAllowForwardingRequestToParent method, kmdf.wdfpdoinitallowforwardingrequesttoparent, wdf.wdfpdoinitallowforwardingrequesttoparent, wdfpdo/WdfPdoInitAllowForwardingRequestToParent
ms.topic: function
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfPdoInitAllowForwardingRequestToParent
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPdoInitAllowForwardingRequestToParent function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfPdoInitAllowForwardingRequestToParent</b> method enables a driver's ability to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a>.


## -parameters




### -param DeviceInit [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure.


## -returns



None.




## -remarks



If your driver uses <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a> to requeue I/O requests from a child device's I/O queue to a parent device's I/O queue, the driver must call <b>WdfPdoInitAllowForwardingRequestToParent</b> before it calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> to create a physical device object (PDO) for the child device. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>.

For more information about <b>WdfPdoInitAllowForwardingRequestToParent</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/requeuing-i-o-requests">Requeuing I/O Requests</a>.


#### Examples

The following code example enables a driver's ability to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfPdoInitAllowForwardingRequestToParent(pDeviceInit);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfrequest/nf-wdfrequest-wdfrequestforwardtoparentdeviceioqueue">WdfRequestForwardToParentDeviceIoQueue</a>
 

 

