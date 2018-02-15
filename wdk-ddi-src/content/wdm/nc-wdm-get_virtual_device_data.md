---
UID: NC:wdm.GET_VIRTUAL_DEVICE_DATA
title: GET_VIRTUAL_DEVICE_DATA
author: windows-driver-content
description: The GetVirtualFunctionData routine reads data from the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.
old-location: pci\getvirtualfunctiondata.htm
old-project: PCI
ms.assetid: 2DE7417D-C616-4D1F-835D-29F477410F1E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PCI.getvirtualfunctiondata, GetVirtualFunctionData routine, GetVirtualFunctionData, GET_VIRTUAL_DEVICE_DATA, GET_VIRTUAL_DEVICE_DATA, wdm/GetVirtualFunctionData
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	GetVirtualFunctionData
product: Windows
targetos: Windows
req.typenames: "*PWDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME"
req.product: Windows 10 or later.
---

# GET_VIRTUAL_DEVICE_DATA callback


## -description


The  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451137">GetVirtualFunctionData</a> routine reads data from the PCI Express (PCIe) configuration space of a virtual function (VF) on a device that supports the single root I/O virtualization (SR-IOV) interface.


## -prototype


````
GET_VIRTUAL_DEVICE_DATA GetVirtualFunctionData;

ULONG GetVirtualFunctionData(
  _Inout_ PVOID  Context,
  _In_    USHORT VirtualFunction,
  _Out_   PVOID  Buffer,
  _In_    ULONG  Offset,
  _In_    ULONG  Length
)
{ ... }
````


## -parameters




### -param Context [in, out]

A pointer to interface-specific context information. The caller passes the value that is passed as the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a> structure for the interface.


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
      <a href="https://msdn.microsoft.com/library/windows/hardware/hh451137">GetVirtualFunctionData</a> routine returns the length, in bytes, of the PCIe configuration data that was read after a successful read operation. If the read operation is unsuccessful, the routine returns zero. 




## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451137">GetVirtualFunctionData</a> routine resembles the <a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a> routine, except that it reads PCIe configuration data from a VF instead of from a device's physical function (PF).

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451137">GetVirtualFunctionData</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a> interface. The <a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a> routine is provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546561">GUID_BUS_INTERFACE_STANDARD</a> interface.

<div class="alert"><b>Note</b>  The virtualization stack calls <a href="https://msdn.microsoft.com/library/windows/hardware/hh451137">GetVirtualFunctionData</a> when a driver that is running in the guest operating system calls the <a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a> routine.</div>
<div> </div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451143">GUID_PCI_VIRTUALIZATION_INTERFACE</a>



<a href="..\wdm\nc-wdm-get_set_device_data.md">GetBusData</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406642">PCI_VIRTUALIZATION_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546561">GUID_BUS_INTERFACE_STANDARD</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [PCI\pci]:%20GET_VIRTUAL_DEVICE_DATA routine%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

