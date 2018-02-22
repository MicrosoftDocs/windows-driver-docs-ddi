---
UID: NF:wdfpdo.WdfPdoRequestEject
title: WdfPdoRequestEject function
author: windows-driver-content
description: The WdfPdoRequestEject method informs the framework that a specified device is about to be ejected from its docking station.
old-location: wdf\wdfpdorequesteject.htm
old-project: wdf
ms.assetid: 40cd83c0-701a-436f-a3c3-b0ab14848a92
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.wdfpdorequesteject, wdfpdo/WdfPdoRequestEject, kmdf.wdfpdorequesteject, WdfPdoRequestEject method, DFDeviceObjectFdoPdoRef_f57ccd07-8cb3-4972-bddb-aa704d9422b0.xml, WdfPdoRequestEject
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfPdoRequestEject
product: Windows
targetos: Windows
req.typenames: "*PWDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO"
req.product: Windows 10 or later.
---

# WdfPdoRequestEject function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfPdoRequestEject</b> method informs the framework that a specified device is about to be ejected from its docking station.


## -syntax


````
VOID WdfPdoRequestEject(
  _In_ WDFDEVICE Device
);
````


## -parameters




### -param Device [in]

A handle to a framework device object that represents the device's physical device object (PDO).


## -returns



None.

A system bug check occurs if the driver supplies an invalid object handle.




## -remarks



A bus driver can call <b>WdfPdoRequestEject</b> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a> to report that the driver has detected an attempt to eject one of its enumerated child devices from the device's docking station. For example, the driver might detect that a user has pushed an eject button. 

If the framework device object for the device's PDO is available, the driver can call <b>WdfPdoRequestEject</b>. If the driver is using dynamic bus enumeration and if the device's identification description is available, the driver can call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a>.

For more information about <b>WdfPdoRequestEject</b> and <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a>, see <a href="https://msdn.microsoft.com/7820bb71-7218-4c5f-af2b-f41e1b5f696d">Supporting Ejectable Devices</a>.


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

<a href="..\wdffdo\nf-wdffdo-wdffdounlockstaticchildlistfromiteration.md">WdfFdoUnlockStaticChildListFromIteration</a>



<a href="..\wdffdo\nf-wdffdo-wdffdolockstaticchildlistforiteration.md">WdfFdoLockStaticChildListForIteration</a>



<a href="..\wdffdo\nf-wdffdo-wdffdoretrievenextstaticchild.md">WdfFdoRetrieveNextStaticChild</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfPdoRequestEject method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

