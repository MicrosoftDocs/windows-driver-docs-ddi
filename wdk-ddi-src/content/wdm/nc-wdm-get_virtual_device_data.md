---
UID: NC:wdm.GET_VIRTUAL_DEVICE_DATA
title: GET_VIRTUAL_DEVICE_DATA (wdm.h)
description: The GetVirtualFunctionData routine reads data from the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: pci\getvirtualfunctiondata.htm
tech.root: PCI
ms.assetid: 2DE7417D-C616-4D1F-835D-29F477410F1E
ms.date: 02/24/2018
ms.keywords: GET_VIRTUAL_DEVICE_DATA, GetVirtualFunctionData, GetVirtualFunctionData routine, PCI.getvirtualfunctiondata, wdm/GetVirtualFunctionData
ms.topic: callback
f1_keywords:
 - "wdm/GetVirtualFunctionData"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in Windows Server 2012 and later versions of Windows.
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Wdm.h
api_name:
- GetVirtualFunctionData
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# GET_VIRTUAL_DEVICE_DATA callback


## -description


The  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_data">GetVirtualFunctionData</a> routine reads data from the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.


## -prototype


```cpp
GET_VIRTUAL_DEVICE_DATA GetVirtualFunctionData;

ULONG GetVirtualFunctionData(
  _Inout_ PVOID  Context,
  _In_    USHORT VirtualFunction,
  _Out_   PVOID  Buffer,
  _In_    ULONG  Offset,
  _In_    ULONG  Length
)
{ ... }
```


## -parameters




### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406642(v=vs.85)">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.


### -param VirtualFunction [in]

A zero-based value that specifies the VF on the device from which data is to be read.


### -param Buffer [out]

A pointer to the buffer that contains the configuration information read from the PCIe configuration space of the VF.


### -param Offset [in]

The offset into the PCIe configuration space data of the VF. This member specifies where this read operation begins.


### -param Length [in]

The length, in bytes, of the data to be read.


## -returns



The
      <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_data">GetVirtualFunctionData</a> routine returns the length, in bytes, of the PCIe configuration data that was read after a successful read operation. If the read operation is unsuccessful, the routine returns zero.




## -remarks



The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_data">GetVirtualFunctionData</a> routine resembles the <a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a> routine, except that it reads PCIe configuration data from a VF instead of from a device's physical function (PF).

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_data">GetVirtualFunctionData</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface. The <a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546561">GUID_BUS_INTERFACE_STANDARD</a> interface.

<div class="alert"><b>Note</b>  The virtualization stack calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-get_virtual_device_data">GetVirtualFunctionData</a> when a driver that is running in the guest operating system calls the <a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a> routine.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546561">GUID_BUS_INTERFACE_STANDARD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/hh406642(v=vs.85)">PCI_VIRTUALIZATION_INTERFACE</a>



<a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a>



<b></b>



 

 


