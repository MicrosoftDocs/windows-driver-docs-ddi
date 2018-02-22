---
UID: NS:pcivirt._MITIGABLE_DEVICE_INTERFACE
title: "_MITIGABLE_DEVICE_INTERFACE"
author: windows-driver-content
description: Stores function pointers to callback functions implemented by the physical function (PF) driver for the mitigable device interface.
old-location: pci\mitigable_device_interface.htm
old-project: PCI
ms.assetid: 1fac7c03-2a48-4b29-951d-c777fbec7dd3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: pcivirt/MITIGABLE_DEVICE_INTERFACE, MITIGABLE_DEVICE_INTERFACE, MITIGABLE_DEVICE_INTERFACE structure [Buses], _MITIGABLE_DEVICE_INTERFACE, PCI.mitigable_device_interface, *PMITIGABLE_DEVICE_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pcivirt.h
req.include-header: 
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Pcivirt.h
apiname:
-	MITIGABLE_DEVICE_INTERFACE
product: Windows
targetos: Windows
req.typenames: MITIGABLE_DEVICE_INTERFACE, *PMITIGABLE_DEVICE_INTERFACE
---

# _MITIGABLE_DEVICE_INTERFACE structure


## -description


Stores function pointers to callback functions implemented by the physical function (PF) driver  for the mitigable device interface.


## -syntax


````
typedef struct _MITIGABLE_DEVICE_INTERFACE {
  USHORT                         Size;
  USHORT                         Version;
  PVOID                          Context;
  PINTERFACE_REFERENCE           InterfaceReference;
  PINTERFACE_REFERENCE           InterfaceDereference;
  PREAD_WRITE_MITIGATED_REGISTER ReadWriteMitigatedRegister;
} MITIGABLE_DEVICE_INTERFACE, MITIGABLE_DEVICE_INTERFACE;
````


## -struct-fields




### -field Size

Size of this structure.


### -field Version

Version of this structure


### -field Context

Driver-defined context passed by the driver.


### -field InterfaceReference

Pointer to a routine that increments the number of references to this interface. For more information about this routine, see <a href="..\miniport\nc-miniport-pinterface_reference.md">InterfaceReference</a>. 


### -field InterfaceDereference

Pointer to a routine that decrements the number of references to this interface. For more information about this routine, see <a href="..\miniport\nc-miniport-pinterface_dereference.md">InterfaceDereference</a>. 


### -field ReadWriteMitigatedRegister

Pointer to the driver's implementation of the <a href="https://msdn.microsoft.com/7cd45484-0fee-4b8e-aa35-4142883c146e">READ_WRITE_MITIGATED_REGISTER</a> callback function.


## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to reset a specific virtual function. 

The PF driver registers its implementation by setting the <b>ReadVfConfig</b> member of the <a href="https://msdn.microsoft.com/c71add7d-9920-4b2f-a46a-4a09a94f3900">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.



