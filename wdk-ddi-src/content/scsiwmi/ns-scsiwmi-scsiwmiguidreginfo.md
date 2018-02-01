---
UID: NS:scsiwmi.SCSIWMIGUIDREGINFO
title: SCSIWMIGUIDREGINFO
author: windows-driver-content
description: The SCSIWMIGUIDREGINFO structure contains information about a given data or event block supported by a SCSI miniport driver.
old-location: storage\scsiwmiguidreginfo.htm
old-project: storage
ms.assetid: 7116445e-751b-478a-8e58-8f5c90d06b9b
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PSCSIWMIGUIDREGINFO structure pointer [Storage Devices], scsiwmi/PSCSIWMIGUIDREGINFO, SCSIWMIGUIDREGINFO structure [Storage Devices], PSCSIWMIGUIDREGINFO, storage.scsiwmiguidreginfo, SCSIWMIGUIDREGINFO, *PSCSIWMIGUIDREGINFO, structs-scsibus_3688cdd5-2515-4fd8-8eae-37689dac26c0.xml, scsiwmi/SCSIWMIGUIDREGINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
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
-	scsiwmi.h
apiname:
-	SCSIWMIGUIDREGINFO
product: Windows
targetos: Windows
req.typenames: "*PSCSIWMIGUIDREGINFO, SCSIWMIGUIDREGINFO"
req.product: Windows 10 or later.
---

# SCSIWMIGUIDREGINFO structure


## -description


The SCSIWMIGUIDREGINFO structure contains information about a given data or event block supported by a SCSI miniport driver. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef struct {
  LPCGUID Guid;
  ULONG   InstanceCount;
  ULONG   Flags;
} SCSIWMIGUIDREGINFO, *PSCSIWMIGUIDREGINFO;
````


## -struct-fields




### -field Guid

Points to the GUID that identifies the block. 


### -field InstanceCount

Specifies the number of instances defined for the block.


### -field Flags

Indicates characteristics of the block. The SCSI port driver sets all but the following WMIREG_FLAG_<i>XXX</i> on behalf of the miniport driver. A miniport driver might set one or more of the following flags: 




#### WMIREG_FLAG_EVENT_ONLY_GUID

The block can be enabled or disabled as an event only, and cannot be queried or set. If this flag is clear, the block can also be queried or set. 


#### WMIREG_FLAG_EXPENSIVE

Requests the port driver send an enable-collection SRB the first time a data consumer opens the data block and a disable-collection SRB when the last data consumer closes the data block. This is recommended if collecting such data affects performance. A miniport driver need not collect the data until a data consumer explicitly requests it by opening the block. 


#### WMIREG_FLAG_REMOVE_GUID

Removes support for a previously registered block when set.


## -remarks


The miniport driver passes a pointer to a SCSI_WMILIB_CONTEXT which contains a SCSIWMIREGGUID array in the <i>WmiLibInfo</i> parameter of <a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>. The miniport driver passes this information each time it calls <b>ScsiPortWmiDispatchFunction</b>. Each SCSIWMIREGGUID structure in the array represents one of the miniport driver's data or event blocks. 

A miniport driver's SCSIWMIREGGUID array should include any standard data blocks defined in <i>wmicore.mof</i> for its device type, and might include miniport driver-defined data and event blocks. A miniport driver defines custom data and event blocks in a MOF file, which is compiled as a resource attached to the miniport driver's binary image and specified in the <i>MofResourceName</i> parameter of the miniport driver's HwScsiWmiQueryReginfo routine. 

For more information about defining blocks, <a href="https://msdn.microsoft.com/5c2ed322-0fc9-4004-9a5f-f4d3c6a59fe9">Windows Management Instrumentation</a>.



## -see-also

<a href="..\scsiwmi\nf-scsiwmi-scsiportwmidispatchfunction.md">ScsiPortWmiDispatchFunction</a>

<a href="..\scsiwmi\ns-scsiwmi-_scsiwmilib_context.md">SCSI_WMILIB_CONTEXT</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557344">HwScsiWmiQueryReginfo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSIWMIGUIDREGINFO structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

