---
UID: NS:ntddcdrm._CDROM_SET_STREAMING
title: _CDROM_SET_STREAMING (ntddcdrm.h)
description: The CDROM_SET_SPEED structure is used with the IOCTL_CDROM_SET_SPEED request to set the spindle speed of a CD-ROM drive during isochronous transfers that permit some data loss.
old-location: storage\cdrom_set_streaming.htm
tech.root: storage
ms.assetid: e5c2d421-5994-4f1d-9022-718500eef1a9
ms.date: 03/29/2018
ms.keywords: "*PCDROM_SET_STREAMING, CDROM_SET_STREAMING, CDROM_SET_STREAMING structure [Storage Devices], PCDROM_SET_STREAMING, PCDROM_SET_STREAMING structure pointer [Storage Devices], _CDROM_SET_STREAMING, ntddcdrm/CDROM_SET_STREAMING, ntddcdrm/PCDROM_SET_STREAMING, storage.cdrom_set_streaming, structs-CD-ROM_5157906e-31d2-42c7-8e90-cc673ed02510.xml"
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdrm.h
api_name:
-	CDROM_SET_STREAMING
product:
- Windows
targetos: Windows
req.typenames: CDROM_SET_STREAMING, *PCDROM_SET_STREAMING
---

# _CDROM_SET_STREAMING structure


## -description


The CDROM_SET_SPEED structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559381">IOCTL_CDROM_SET_SPEED</a> request to set the spindle speed of a CD-ROM drive during isochronous transfers that permit some data loss.


## -struct-fields




### -field RequestType

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551370">CDROM_SPEED_REQUEST</a>-typed value that indicates which multimedia command to use when setting the spindle speed.


### -field ReadSize

The number of kilobytes to read in each unit of time, where a unit of time is specified by <b>ReadTime</b>. A value of 0xFFFF in <b>ReadSize </b>selects the optimal data transfer speed of the drive.


### -field ReadTime

The number of milliseconds in which to read <b>ReadSize</b> kilobytes of data.


### -field WriteSize

The number of kilobytes to write in each unit of time, where a unit of time is defined by <b>WriteTime</b>. A value of 0xFFFF in <b>WriteSize</b> selects the optimal data transfer speed of the drive.


### -field WriteTime

The number of milliseconds in which to write <b>WriteSize</b> kilobytes of data.


### -field StartLba

The first logical block address, in bytes, of the IOCTL_CDROM_SET_SPEED request.


### -field EndLba

The last logical block address, in bytes, of the IOCTL_CDROM_SET_SPEED request.


### -field RotationControl

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff568045">WRITE_ROTATION</a>-typed value that indicates whether the device will write to the media by using CLV (constant linear velocity) rotation or CLA (constant angular velocity) rotation.


### -field RestoreDefaults

A BOOLEAN value that, when <b>TRUE</b>, instructs the CD-ROM class driver to make the CD-ROM drive run at its default spindle speed. A value of <b>FALSE</b> instructs the class driver to calculate the spindle speed from the <b>ReadSize</b>, <b>ReadTime</b>, <b>WriteSize</b>, and <b>WriteTime</b> members of this structure.


### -field SetExact

A BOOLEAN value that, when <b>TRUE</b>, instructs the CD-ROM class driver to set the CD-ROM drive to the exact speed that is specified by the <b>ReadSize</b>, <b>ReadTime</b>, <b>WriteSize</b>, and <b>WriteTime</b> members of this structure. If the class driver cannot set the spindle speed to the exact value that is specified by these members, it fails the request. A value of <b>FALSE</b> in <b>SetExact </b>instructs the class driver to make the spindle speed of the drive match as closely as possible the speed that is specified by <b>ReadSize</b>, <b>ReadTime</b>, <b>WriteSize</b>, and <b>WriteTime</b>; the class driver does not fail the request if the drive cannot run at the exact value that these members specify.


### -field RandomAccess

A BOOLEAN value that, when <b>TRUE</b>, instructs the CD-ROM class driver to configure the CD-ROM drive, so that it will switch back and forth between read and write operations to maximize performance (data throughput), even if switching between read and write operations causes a particular read or write operation to occur more slowly. In other words, a value of <b>TRUE</b> in <b>RandomAccess</b> permits the drive to lower the speed of some individual read and write operations to ensure better overall performance in data transfers. A value of <b>FALSE</b> instructs the CD-ROM class driver to configure the CD-ROM drive to guarantee the speeds of read and write operations, independent of one another. The data transfer rate of each operation is rigid, and the drive will not alter the speed to achieve performance gains.


### -field Persistent

A BOOLEAN value that, when <b>TRUE</b>, instructs the CD-ROM class driver to configure the CD-ROM drive to restore the default speed when the user changes the media. A value of <b>FALSE</b>  instructs the CD-ROM class driver to configure the CD-ROM drive to maintain its speed until the computer restarts or the class driver changes the speed with another command.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551368">CDROM_SET_SPEED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551370">CDROM_SPEED_REQUEST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559381">IOCTL_CDROM_SET_SPEED</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568045">WRITE_ROTATION</a>
 

 

