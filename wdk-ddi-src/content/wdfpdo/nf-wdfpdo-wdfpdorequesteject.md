---
UID: NF:wdfpdo.WdfPdoRequestEject
title: WdfPdoRequestEject function
author: windows-driver-content
description: The WdfPdoRequestEject method informs the framework that a specified device is about to be ejected from its docking station.
old-location: wdf\wdfpdorequesteject.htm
tech.root: wdf
ms.assetid: 40cd83c0-701a-436f-a3c3-b0ab14848a92
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_f57ccd07-8cb3-4972-bddb-aa704d9422b0.xml, WdfPdoRequestEject, WdfPdoRequestEject method, kmdf.wdfpdorequesteject, wdf.wdfpdorequesteject, wdfpdo/WdfPdoRequestEject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfpdo.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfPdoRequestEject
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfPdoRequestEject function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoRequestEject</b> method informs the framework that a specified device is about to be ejected from its docking station.


## -parameters




### -param Device [in]

A handle to a framework device object that represents the device's physical device object (PDO).


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



A bus driver can call <b>WdfPdoRequestEject</b> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545641">WdfChildListRequestChildEject</a> to report that the driver has detected an attempt to eject one of its enumerated child devices from the device's docking station. For example, the driver might detect that a user has pushed an eject button. 

If the framework device object for the device's PDO is available, the driver can call <b>WdfPdoRequestEject</b>. If the driver is using dynamic bus enumeration and if the device's identification description is available, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545641">WdfChildListRequestChildEject</a>.

For more information about <b>WdfPdoRequestEject</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545641">WdfChildListRequestChildEject</a>, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.


#### Examples

The following code example searches a list of child devices to find one that matches a specified serial number. When the example finds the correct child, it calls <b>WdfPdoRequestEject</b> to indicate that the child is being ejected. This example was taken from the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">Toaster</a> sample bus driver and simplified.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFDEVICE  hChild = NULL;
NTSTATUS  status = STATUS_INVALID_PARAMETER;
PPDO_DEVICE_DATA  pdoData;

WdfFdoLockStaticChildListForIteration(Device);

while ((hChild = WdfFdoRetrieveNextStaticChild(
                                               Device, 
                                               hChild,
                                               WdfRetrieveAddedChildren
                                               )) != NULL) {
    //
    // Obtain device object context space, and check the
    // stored serial number.
    //
    pdoData = PdoGetData(hChild);
    if (SerialNo == pdoData-&gt;SerialNo) {
        status = STATUS_SUCCESS;
        WdfPdoRequestEject(hChild);
    }
}
WdfFdoUnlockStaticChildListFromIteration(Device);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547293">WdfFdoRetrieveNextStaticChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547297">WdfFdoUnlockStaticChildListFromIteration</a>
 

 

