---
UID: NF:wdfdevice.WdfDeviceSetBusInformationForChildren
title: WdfDeviceSetBusInformationForChildren function
author: windows-driver-content
description: The WdfDeviceSetBusInformationForChildren method sets information about a bus that a bus driver supports. This information is available to the bus's child devices.
old-location: wdf\wdfdevicesetbusinformationforchildren.htm
old-project: wdf
ms.assetid: ecfce692-7dac-4f55-8a8a-1f51c27cce41
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectGeneralRef_76b69a67-0e1e-41d6-be98-3d5f76433d97.xml, WdfDeviceSetBusInformationForChildren, wdf.wdfdevicesetbusinformationforchildren, wdfdevice/WdfDeviceSetBusInformationForChildren, kmdf.wdfdevicesetbusinformationforchildren, WdfDeviceSetBusInformationForChildren method
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfDeviceSetBusInformationForChildren
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceSetBusInformationForChildren function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceSetBusInformationForChildren</b> method sets information about a bus that a bus driver supports. This information is available to the bus's child devices.


## -syntax


````
VOID WdfDeviceSetBusInformationForChildren(
  _In_ WDFDEVICE            Device,
  _In_ PPNP_BUS_INFORMATION BusInformation
);
````


## -parameters




### -param Device [in]

A handle to a framework device object.


### -param BusInformation [in]

A pointer to a caller-allocated <a href="..\wdm\ns-wdm-_pnp_bus_information.md">PNP_BUS_INFORMATION</a> structure that describes the bus.


## -returns



None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



Child devices can obtain the information that <b>WdfDeviceSetBusInformationForChildren</b> supplies by calling <a href="..\wdffdo\nf-wdffdo-wdffdoinitqueryproperty.md">WdfFdoInitQueryProperty</a> or <a href="..\wdfdevice\nf-wdfdevice-wdfdevicequeryproperty.md">WdfDeviceQueryProperty</a>.


#### Examples

The following code example initializes a PNP_BUS_INFORMATION structure and then calls <b>WdfDeviceSetBusInformationForChildren</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PNP_BUS_INFORMATION  busInfo;

busInfo.BusTypeGuid = GUID_DEVCLASS_TOASTER;
busInfo.LegacyBusType = PNPBus;
busInfo.BusNumber = 0;

WdfDeviceSetBusInformationForChildren(
                                      device,
                                      &amp;busInfo
                                      );</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdm\ns-wdm-_pnp_bus_information.md">PNP_BUS_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceSetBusInformationForChildren method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

