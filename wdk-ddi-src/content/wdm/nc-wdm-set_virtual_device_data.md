---
UID: NC:wdm.SET_VIRTUAL_DEVICE_DATA
title: SET_VIRTUAL_DEVICE_DATA
author: windows-driver-content
description: The SetVirtualFunctionData routine writes data to the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: pci\setvirtualfunctiondata.htm
tech.root: PCI
ms.assetid: 12CC6973-E691-425E-A8E8-839F83116D29
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PCI.setvirtualfunctiondata, SET_VIRTUAL_DEVICE_DATA, SetVirtualFunctionData, SetVirtualFunctionData routine, wdm/SetVirtualFunctionData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	SetVirtualFunctionData
product:
- Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---

# SET_VIRTUAL_DEVICE_DATA callback


## -description


The  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451552">SetVirtualFunctionData</a> routine writes data to the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.


## -prototype


```
SET_VIRTUAL_DEVICE_DATA SetVirtualFunctionData;

ULONG SetVirtualFunctionData(
  _Inout_ PVOID  Context,
  _In_    USHORT VirtualFunction,
  _In_    PVOID  Buffer,
  _In_    ULONG  Offset,
  _In_    ULONG  Length
)
{ ... }
```


## -parameters




### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.


### -param VirtualFunction [in]

A zero-based value that specifies the VF on the device from which data is to be written.


### -param Buffer [in]

A pointer to the buffer that contains the configuration information to be written to the PCIe configuration space of the VF.


### -param Offset [in]

The offset into the PCIe configuration space data of the VF. This member specifies where this write operation begins.


### -param Length [in]

The length, in bytes, of the data to be written.


## -returns



The
      <a href="https://msdn.microsoft.com/library/windows/hardware/hh451552">SetVirtualFunctionData</a> routine returns the length, in bytes, of the PCIe configuration data that was written after a successful write operation. If the write operation is unsuccessful, the routine returns zero.




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451552">SetVirtualFunctionData</a> routine is similar to the <a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a> routine, except that it writes PCIe configuration data to a VF instead of to a device's physical function (PF).

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451552">SetVirtualFunctionData</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface. The <a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546561">GUID_BUS_INTERFACE_STANDARD</a> interface.

<div class="alert"><b>Note</b>  The virtualization stack calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh451552">SetVirtualFunctionData</a> when a driver that is running in the guest operating system calls the <a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a> routine.</div>
<div> </div>



## -see-also

<a href="..\wdm\nc-wdm-get_set_device_data.md">SetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<b></b>



 

 


