---
UID: NC:wdm.GET_SET_DEVICE_DATA
title: GET_SET_DEVICE_DATA
author: windows-driver-content
description: The GetBusData routine reads data from the device's configuration space.
old-location: kernel\getbusdata.htm
old-project: kernel
ms.assetid: F5BDB3DF-6AC9-424E-BC69-27071F3D3820
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: GET_SET_DEVICE_DATA, GetBusData, GetBusData routine [Kernel-Mode Driver Architecture], drvr_interface_f4fd2eab-5924-4ffa-b39e-fd7e0f74e5df.xml, kernel.busgetdevicedata, kernel.getbusdata, wdm/GetBusData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Ntddk.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wdm.h
api_name:
-	GetBusData
product: Windows
targetos: Windows
req.typenames: 
---

# GET_SET_DEVICE_DATA callback function


## -description


The <i>GetBusData</i> routine reads data from the device's configuration space. 


## -parameters




### -param Context [in]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540707">BUS_INTERFACE_STANDARD</a> structure for the interface.


### -param DataType [in]

The type of bus data to read. For more information, see the discussion of the <i>WhichSpace</i> parameter in <a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>. 


### -param Buffer [in]

A pointer to the buffer that holds the configuration information to be read from the device's configuration space. 


### -param Offset [in]

The offset into the bus-specific device data where this read operation begins. For example, if the <i>DataType</i> parameter is <b>PCI_WHICHSPACE_CONFIG</b>, the <i>Offset</i> parameter value is the offset into PCI Configuration Space. 


### -param Length [in]

The length, in bytes, of data to read. 


## -returns



The <i>GetBusData</i> routine returns the length, in bytes, of the configuration data that is read after a successful read operation. If the read operation is unsuccessful, a value of zero is returned. 




## -remarks



Depending on the value of the <i>DataType</i> parameter, the <i>GetBusData</i> routine can be called only from the interrupt request levels (IRQLs) that are defined in the following table.

<table>
<tr>
<th><i>DataType</i> value</th>
<th>IRQL</th>
</tr>
<tr>
<td>
<b>PCI_WHICHSPACE_CONFIG</b>

</td>
<td>
&lt;= DIRQL

</td>
</tr>
<tr>
<td>
<b>PCI_WHICHSPACE_ROM </b>

</td>
<td>
&lt;= APC_LEVEL

</td>
</tr>
<tr>
<td>
<b>PCCARD_COMMON_MEMORY</b>

<b>PCCARD_COMMON_MEMORY_INDIRECT</b>

</td>
<td>
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<td>
<b>PCCARD_ATTRIBUTE_MEMORY</b>

<b>PCCARD_ATTRIBUTE_MEMORY_INDIRECT</b>

</td>
<td>
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<td>
<b>PCCARD_PCI_CONFIGURATION_SPACE</b>

</td>
<td>
&lt;= DIRQL

</td>
</tr>
</table>
 

The following remarks apply to drivers for PCI Express (PCIe) virtual functions (VFs) on devices that support the single root I/O virtualization (SR-IOV) interface:

<ul>
<li>
Drivers for PCIe VFs should call the <i>GetBusData</i> routine at IRQL &lt;= APC_LEVEL.

</li>
<li>
In order to read PCI Configuration data for the VF at IRQL = DISPATCH_LEVEL, the driver must issue I/O requests of <a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540707">BUS_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551727">IRP_MN_READ_CONFIG</a>
 

 

