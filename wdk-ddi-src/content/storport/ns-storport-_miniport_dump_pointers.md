---
UID: NS:storport._MINIPORT_DUMP_POINTERS
title: "_MINIPORT_DUMP_POINTERS"
author: windows-driver-content
description: A Storport miniport driver uses this structure to support the SCSI_REQUEST_BLOCK (SRB) function code SRB_FUNCTION_DUMP_POINTERS.
old-location: storage\miniport_dump_pointers.htm
old-project: storage
ms.assetid: a61da8e7-6db0-4d89-bf68-8fa74c284720
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PMINIPORT_DUMP_POINTERS, storage.miniport_dump_pointers, PMINIPORT_DUMP_POINTERS structure pointer [Storage Devices], storport/MINIPORT_DUMP_POINTERS, storport/PMINIPORT_DUMP_POINTERS, MINIPORT_DUMP_POINTERS, structs-virtual_34ca963f-93fe-4e7d-8e02-02bde32cf2ef.xml, MINIPORT_DUMP_POINTERS structure [Storage Devices], *PMINIPORT_DUMP_POINTERS, _MINIPORT_DUMP_POINTERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Storport.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	storport.h
apiname:
-	MINIPORT_DUMP_POINTERS
product: Windows
targetos: Windows
req.typenames: "*PMINIPORT_DUMP_POINTERS, MINIPORT_DUMP_POINTERS"
req.product: Windows 10 or later.
---

# _MINIPORT_DUMP_POINTERS structure


## -description


A Storport miniport driver uses this structure to support the <a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a> (SRB) function code SRB_FUNCTION_DUMP_POINTERS. When a miniport driver receives this kind of SRB, the <b>DataBuffer</b> SRB member points to a <b>MINIPORT_DUMP_POINTERS</b> structure. This SRB is sent to the miniport driver that is used to control the disk that holds the crash dump data after the SRB was returned from the miniport driver's <a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a> routine. Virtual miniport drivers are required to support SRB_FUNCTION_DUMP_POINTERS.


## -syntax


````
typedef struct _MINIPORT_DUMP_POINTERS {
  USHORT                 Version;
  USHORT                 Size;
  WCHAR                  DriverName[DUMP_MINIPORT_NAME_LENGTH];
  struct _ADAPTER_OBJECT  *AdapterObject;
  PVOID                  MappedRegisterBase;
  ULONG                  CommonBufferSize;
  PVOID                  MiniportPrivateDumpData;
  ULONG                  SystemIoBusNumber;
  INTERFACE_TYPE         AdapterInterfaceType;
  ULONG                  MaximumTransferLength;
  ULONG                  NumberOfPhysicalBreaks;
  ULONG                  AlignmentMask;
  ULONG                  NumberOfAccessRanges;
  ACCESS_RANGE           (*AccessRanges)[];
  UCHAR                  NumberOfBuses;
  BOOLEAN                Master;
  BOOLEAN                MapBuffers;
  UCHAR                  MaximumNumberOfTargets;
} MINIPORT_DUMP_POINTERS, *PMINIPORT_DUMP_POINTERS;
````


## -struct-fields




### -field Version

Set to DUMP_MINIPORT_VERSION_1.


### -field Size

Set to sizeof(MINIPORT_DUMP_POINTERS).


### -field DriverName

The wide-character name of the miniport driver without path information (for example, Miniport.sys).


### -field AdapterObject

Set to <b>NULL</b>.


### -field _ADAPTER_OBJECT

 


### -field MappedRegisterBase

Set to zero.


### -field CommonBufferSize

The size of the common buffer that is required. The size must not be greater than 64 KB (65,536 bytes).


### -field MiniportPrivateDumpData

The context that is to be passed to the miniport driver's <a href="..\storport\nc-storport-hw_find_adapter.md">HwStorFindAdapter</a> routine during the crash dump. The context is passed in the <b>Reserved</b> member or, starting with Windows 8, the <b>MiniportDumpData</b> member of the <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structure.


### -field SystemIoBusNumber

Specifies the system-assigned number of the I/O bus to which the HBA is connected. The Storport driver initializes this member. Miniport drivers that work with the Storport driver must not change this member. For more information, see the <b>SystemIoBusNumber</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. 


### -field AdapterInterfaceType

Identifies the I/O bus interface. The Storport driver initializes this member. Miniport drivers that work with the Storport driver must not modify this member. For more information, see the <b>AdapterInterfaceType</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. 


### -field MaximumTransferLength

Specifies the maximum number of bytes the HBA can transfer in a single transfer operation in crashdump mode. By default, the value of this member is SP_UNINITIALIZED_VALUE, which indicates an unlimited maximum transfer size. This value is specific to the dump operation of the miniport and may differ from the value in the <b>MaximumTransferLength</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. 


### -field NumberOfPhysicalBreaks

Specifies the maximum number of breaks between address ranges that a data buffer can have to create scatter/gather lists. In other words, the number of scatter/gather list entries that the adapter can support minus one. For more information, see the <b>NumberOfPhysicalBreaks</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. 


### -field AlignmentMask

Contains a mask that indicates the alignment restrictions for buffers that are required by the HBA for transfer operations. Valid mask values are also restricted by characteristics of the memory managers on different versions of the Microsoft Windows operating systems. The valid mask values are 0 (byte aligned), 0x1 (word aligned), 0x3 (DWORD aligned), and 0x7 (double DWORD aligned). The miniport driver should set this mask if the HBA supports scatter/gather. The same considerations apply to the <b>AlignmentMask</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. 


### -field NumberOfAccessRanges

Specifies the number of <b>AccessRanges</b> elements in the array. For more information, see the <b>NumberOfAccessRanges</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. 


### -field AccessRanges

 


### -field NumberOfBuses

Specifies the number of buses that are controlled by the adapter. By default, the value of this member is zero. For more information, see the <b>NumberOfBuses</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. 


### -field Master

Indicates, when <b>TRUE</b>, that the HBA is a bus master. The Storport driver initializes this member to <b>TRUE</b>, because its miniport drivers must support bus-mastering DMA. Miniport drivers that work with the Storport driver must not change this value. For more information, see the <b>Master</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. 


### -field MapBuffers

Indicates whether the Storport driver maps SRB data buffer addresses to system virtual addresses. For more information, see the <b>MapBuffers</b> member of <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a>.


### -field MaximumNumberOfTargets

Specifies the number of target peripherals that the adapter can control. For more information, see the <b>MaximumNumberOfTargets</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>. 


#### - (*AccessRanges)

A pointer to an array of ACCESS_RANGE-type elements. The Storport driver initializes this member. Miniport drivers that work with the Storport driver must not change this member. For more information, see the <b>AccessRanges</b> member of <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>.


## -remarks



Starting with Windows 8, physical minport drivers can optionally support SRB_FUNCTION_DUMP_POINTERS. If a physical miniport supports this function, it must set the STOR_FEATURE_DUMP_POINTERS flag in the <b>FeatureSupport</b> member of the <a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure before calling <a href="..\storport\nf-storport-storportinitialize.md">StorPortInitialize</a>. Physical miniports are required to set at least the <b>Version</b> and <b>Size</b> members of <b>MINIPORT_DUMP_POINTERS</b>. Also, if different from the value given in <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>, the <b>MaximumTransferLength</b> member is required for a physical miniport.




## -see-also

<a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a>



<a href="..\storport\nc-storport-hw_initialize.md">HwStorInitialize</a>



<a href="..\srb\ns-srb-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>



<a href="..\storport\ns-storport-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MINIPORT_DUMP_POINTERS structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

