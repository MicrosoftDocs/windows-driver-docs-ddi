---
UID: NF:wdfiotarget.WdfIoTargetWdmGetTargetPhysicalDevice
title: WdfIoTargetWdmGetTargetPhysicalDevice function
description: The WdfIoTargetWdmGetTargetPhysicalDevice method returns a pointer to the Windows Driver Model (WDM) physical device object (PDO) that represents a remote I/O target's device.
old-location: wdf\wdfiotargetwdmgettargetphysicaldevice.htm
tech.root: wdf
ms.assetid: ad24f1b4-ac7f-46df-8f8d-14c956c73a34
ms.date: 02/26/2018
ms.keywords: DFIOTargetRef_43beb595-b555-4253-8a54-495e9e14f071.xml, WdfIoTargetWdmGetTargetPhysicalDevice, WdfIoTargetWdmGetTargetPhysicalDevice method, kmdf.wdfiotargetwdmgettargetphysicaldevice, wdf.wdfiotargetwdmgettargetphysicaldevice, wdfiotarget/WdfIoTargetWdmGetTargetPhysicalDevice
ms.topic: function
req.header: wdfiotarget.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfIoTargetWdmGetTargetPhysicalDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfIoTargetWdmGetTargetPhysicalDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfIoTargetWdmGetTargetPhysicalDevice</b> method returns a pointer to the Windows Driver Model (WDM) physical device object (PDO) that represents a remote I/O target's device.


## -parameters




### -param IoTarget [in]

A handle to a remote I/O target object. This handle was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>.


## -returns



If the I/O target represents a PnP device, <b>WdfIoTargetWdmGetTargetPhysicalDevice</b> returns a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure that represents a remote I/O target's PDO. Otherwise the method returns <b>NULL</b>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The pointer that the <b>WdfIoTargetWdmGetTargetPhysicalDevice</b> method returns is valid until the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548586">WdfIoTargetClose</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548589">WdfIoTargetCloseForQueryRemove</a>, or until the remote I/O target object is deleted. If the driver provides an <a href="https://msdn.microsoft.com/aba2efca-7d1f-4594-af65-13356f0e3f8b">EvtCleanupCallback</a> function for the remote I/O target object, and if the object is deleted before the remote I/O target is closed, the pointer is valid until the <i>EvtCleanupCallback</i> function returns.

If the driver attempts to access the WDM device object after it has been removed, the driver can cause the system to crash.  The <a href="https://go.microsoft.com/fwlink/p/?linkid=251907">toastmon</a> sample demonstrates how the driver can provide an <a href="https://msdn.microsoft.com/cb7c97e5-081e-44fc-a759-9a1ae81de41c">EvtIoTargetQueryRemove</a> callback function so that it is notified if the I/O target is removed.

For more information about <b>WdfIoTargetWdmGetTargetPhysicalDevice</b>, see <a href="https://msdn.microsoft.com/70ae920e-de2d-4014-bae4-74058b26e7c0">Obtaining Information About a General I/O Target</a>. 

For more information about I/O targets, see <a href="https://msdn.microsoft.com/77fd1b64-c3a9-4e12-ac69-0e3725695795">Using I/O Targets</a>.


#### Examples

The following code example obtains a pointer to a DEVICE_OBJECT structure that represents the PDO of a remote I/O target's device. 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PDEVICE_OBJECT  pTargetDO;

pTargetDO = WdfIoTargetWdmGetTargetPhysicalDevice(IoTarget);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548591">WdfIoTargetCreate</a>
 

 

