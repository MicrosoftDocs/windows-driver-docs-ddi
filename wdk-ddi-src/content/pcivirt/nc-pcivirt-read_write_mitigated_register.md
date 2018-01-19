---
UID: NC:pcivirt.READ_WRITE_MITIGATED_REGISTER
title: READ_WRITE_MITIGATED_REGISTER
author: windows-driver-content
description: Reads or writes to mitigated address spaces.
old-location: pci\read_write_mitigated_registers.htm
old-project: PCI
ms.assetid: 7cd45484-0fee-4b8e-aa35-4142883c146e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _PARCLASS_INFORMATION, PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: *PREAD_WRITE_MITIGATED_REGISTER
req.alt-loc: Pcivirt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# READ_WRITE_MITIGATED_REGISTER callback



## -description
Reads or writes to mitigated address spaces. 



## -prototype

````
READ_WRITE_MITIGATED_REGISTER ReadWriteMitigatedRegister;

NTSTATUS ReadWriteMitigatedRegister(
  _In_    PVOID     Context,
  _In_    USHORT    VfIndex,
  _In_    BOOLEAN   Read,
  _In_    USHORT    BarIndex,
  _In_    ULONGLONG Offset,
  _In_    ULONG     Length,
  _Inout_ PUCHAR    Data
)
{ ... }

typedef READ_WRITE_MITIGATED_REGISTER *PREAD_WRITE_MITIGATED_REGISTER;
````


## -parameters

### -param Context [in]

A pointer to a driver-defined context.
                    
                


### -param VfIndex [in]

A zero-based index of the VF to which this read/write operation applies.


### -param Read [in]


                    
                A boolean that indicates whether to perform a read or a write operation. TRUE indicates read, FALSE otherwise.


### -param BarIndex [in]

The BAR that maps the address space being mitigated.


### -param Offset [in]

The offset in number of bytes into the BAR at which this access begins.


### -param Length [in]


                    
                The length in bytes of this read or write operation.


### -param Data [in, out]

A pointer to a buffer that contains the data to read or write.


## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> error code.


## -remarks
This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to read or write from a mitigable register. 

The PF driver registers its implementation by setting the <b>ReadWriteMitigatedRegister</b> member of the <a href="https://msdn.microsoft.com/1fac7c03-2a48-4b29-951d-c777fbec7dd3">MITIGABLE_DEVICE_INTERFACE</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.</p>