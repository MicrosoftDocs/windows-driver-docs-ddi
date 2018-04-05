---
UID: NF:wdffdo.WdfFdoRetrieveNextStaticChild
title: WdfFdoRetrieveNextStaticChild function
author: windows-driver-content
description: The WdfFdoRetrieveNextStaticChild method retrieves a handle to the next framework device object in a list of child devices.
old-location: wdf\wdffdoretrievenextstaticchild.htm
old-project: wdf
ms.assetid: ee0f458b-c8b3-46e7-87bd-25599d39203d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_013cf620-08fe-4c72-8a5e-c7e38a37b503.xml, WdfFdoRetrieveNextStaticChild, WdfFdoRetrieveNextStaticChild method, kmdf.wdffdoretrievenextstaticchild, wdf.wdffdoretrievenextstaticchild, wdffdo/WdfFdoRetrieveNextStaticChild
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
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
-	WdfFdoRetrieveNextStaticChild
product:
- Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WdfFdoRetrieveNextStaticChild function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfFdoRetrieveNextStaticChild</b> method retrieves a handle to the next framework device object in a list of child devices.


## -parameters




### -param Fdo [in]

A handle to a framework device object that represents the parent device.


### -param PreviousChild [in, optional]

A handle to a framework device object that represents the child device that was returned by a previous call to <b>WdfFdoRetrieveNextStaticChild</b>. For the first call to <b>WdfFdoRetrieveNextStaticChild</b>, this value must be <b>NULL</b>.


### -param Flags [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552507">WDF_RETRIEVE_CHILD_FLAGS</a>-typed enumerator value that identifies the type of child devices that the method should retrieve. This parameter cannot be zero. 


## -returns



If the operation succeeds, the method returns a handle to a framework device object. Otherwise it returns <b>NULL</b>.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



Bus drivers that use static bus enumeration can call <b>WdfFdoRetrieveNextStaticChild</b>. 

To retrieve the items in a list of child devices, the driver should:

<ol>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a> to lock the child list.

</li>
<li>
Repeatedly call <b>WdfFdoRetrieveNextStaticChild</b> to obtain the items in the list, one at a time, until the method returns <b>NULL</b>.

</li>
<li>
Call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547297">WdfFdoUnlockStaticChildListFromIteration</a> to unlock the child list.

</li>
</ol>
For more information about static child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.


#### Examples

The following code example searches a static child list until it finds a child device with a serial number that matches a specific value. For other example uses of <b>WdfFdoRetrieveNextStaticChild</b>, see the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/sample-kmdf-drivers">Toaster</a> sample bus driver.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PPDO_DEVICE_DATA  pdoData;
WDFDEVICE  hChild;
NTSTATUS  status = STATUS_INVALID_PARAMETER;

WdfFdoLockStaticChildListForIteration(Device);

while ((hChild = WdfFdoRetrieveNextStaticChild(
                                               Device,
                                               hChild,
                                               WdfRetrieveAddedChildren
                                               )) != NULL) {
    //
    // Obtain device object context data and check the
    // stored serial number.
    //
    pdoData = PdoGetData(hChild);
    if (SerialNo == pdoData-&gt;SerialNo) {
        status = STATUS_SUCCESS;
        WdfPdoRequestEject(hChild);
        break;
    }
}
WdfFdoUnlockStaticChildListFromIteration(Device);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff547282">WdfFdoLockStaticChildListForIteration</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547297">WdfFdoUnlockStaticChildListFromIteration</a>
 

 

