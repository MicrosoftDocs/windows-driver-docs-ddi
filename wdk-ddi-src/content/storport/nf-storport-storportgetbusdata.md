---
UID: NF:storport.StorPortGetBusData
title: StorPortGetBusData function
author: windows-driver-content
description: The StorPortGetBusData routine retrieves the bus-specific configuration information necessary to initialize the HBA.
old-location: storage\storportgetbusdata.htm
old-project: storage
ms.assetid: 19999e21-1afd-42ac-9809-b8ed4b6ac7e3
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storport/StorPortGetBusData, storage.storportgetbusdata, storprt_fb8cc730-c53e-49b6-abe5-6a0648200d32.xml, StorPortGetBusData, StorPortGetBusData routine [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
-	StorPortGetBusData
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---

# StorPortGetBusData function


## -description


The <b>StorPortGetBusData</b> routine retrieves the bus-specific configuration information necessary to initialize the HBA.


## -syntax


````
ULONG StorPortGetBusData(
  _In_    PVOID DeviceExtension,
  _In_    ULONG BusDataType,
  _In_    ULONG SystemIoBusNumber,
  _In_    ULONG SlotNumber,
  _Inout_ PVOID Buffer,
  _In_    ULONG Length
);
````


## -parameters




### -param DeviceExtension [in]

Pointer to the miniport driver's per-HBA storage area.


### -param BusDataType [in]

Contains a value of type <a href="..\miniport\ne-miniport-_bus_data_type.md">BUS_DATA_TYPE</a> that specifies the type of bus-specific configuration data to be returned. Currently, this value can be one of the following: <b>Cmos</b>, <b>EisaConfiguration</b>, <b>Pos</b>, or <b>PCIConfiguration</b>. However, additional types of bus configuration will be supported in the future. The upper bound on the types supported is always <b>MaximumBusDataType</b>.


### -param SystemIoBusNumber [in]

Specifies the system-assigned number of the I/O bus. The miniport driver's <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine obtains this value from the <b>SystemIoBusNumber</b> member initially set in <a href="..\srb\ns-srb-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>.


### -param SlotNumber [in]

Specifies the logical slot number or location of the device.

If <b>PCIConfiguration</b> is specified as the <i>BusDataType</i>, this parameter must be specified as a PCI_SLOT_NUMBER-type value.


### -param Buffer [in, out]

Pointer to a buffer or area to which the configuration data is returned or, if the given <i>Length</i> is zero, points to a location to which the OS-specific port driver returns a pointer to a buffer that it allocates.


### -param Length [in]

Specifies the maximum number of bytes to return at <i>Buffer</i>, or zero if the caller requires the OS-specific port driver to allocate a buffer to contain the data.


## -returns



<b>StorPortGetBusData</b> returns the number of bytes of configuration information it stored in the buffer. When the input <i>BusDataType</i> is <b>PCIConfiguration</b>, <b>StorPortGetBusData</b> can return either of the following values to indicate an error.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>0 (zero)</b></dt>
</dl>
</td>
<td width="60%">
The PCI bus does not exist.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>2</b></dt>
</dl>
</td>
<td width="60%">
The PCI bus exists, but there is no device at the given PCI <i>SlotNumber</i>. The <i>Buffer</i> contains the value PCI_INVALID_VENDOR_ID at the PCI_COMMON_CONFIG <b>VendorId</b> member.

</td>
</tr>
</table>
 




## -remarks



<b>StorPortGetBusData</b> can be called only from a miniport driver's <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine or from <a href="..\storport\nc-storport-hw_adapter_control.md">HwStorAdapterControl</a> when the control type is <b>ScsiSetRunningConfig</b>. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.

Configuration data returned by <b>StorPortGetBusData</b> is valid only until the miniport driver calls <b>StorPortGetBusData</b> again. As soon as the caller's <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine returns control, any returned configuration data becomes invalid.




## -see-also

<a href="..\srb\ns-srb-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>



<a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortGetBusData routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

