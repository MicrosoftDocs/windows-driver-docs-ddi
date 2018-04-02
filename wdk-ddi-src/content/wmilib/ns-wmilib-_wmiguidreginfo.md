---
UID: NS:wmilib._WMIGUIDREGINFO
title: "_WMIGUIDREGINFO"
author: windows-driver-content
description: The WMIGUIDREGINFO structure contains registration information for a given data block or event block exposed by a driver that uses the WMI library support routines.
old-location: kernel\wmiguidreginfo.htm
old-project: kernel
ms.assetid: 8bf36e54-5caa-4dc6-b659-ea0c1ac450f0
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PWMIGUIDREGINFO, PWMIGUIDREGINFO, PWMIGUIDREGINFO structure pointer [Kernel-Mode Driver Architecture], WMIGUIDREGINFO, WMIGUIDREGINFO structure [Kernel-Mode Driver Architecture], _WMIGUIDREGINFO, kernel.wmiguidreginfo, kstruct_d_aeedb315-3e08-4af9-9a37-afd06166a662.xml, wmilib/PWMIGUIDREGINFO, wmilib/WMIGUIDREGINFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wmilib.h
req.include-header: Wmilib.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wmilib.h
api_name:
-	WMIGUIDREGINFO
product: Windows
targetos: Windows
req.typenames: WMIGUIDREGINFO, *PWMIGUIDREGINFO
req.product: Windows 10 or later.
---

# _WMIGUIDREGINFO structure


## -description


The <b>WMIGUIDREGINFO</b> structure contains registration information for a given data block or event block exposed by a driver that uses the WMI library support routines.


## -struct-fields




### -field Guid

Pointer to the GUID that identifies the block. The memory that contains the GUID can be paged unless it is also used to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff565807">WmiFireEvent</a>.


### -field InstanceCount

Specifies the number of instances defined for the block.


### -field Flags

Flag bits that indicate characteristics of the block. These flag bits are defined in the Wmistr.h header file. WMI ORs the <b>Flags</b> parameter value with the flag bits set by the driver in the <i>RegFlags</i> parameter of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff544097">DpWmiQueryReginfo</a> routine, which apply to all of the data blocks and event blocks registered by the driver. <b>Flags</b> therefore supplements the driver's default settings for a given block.

A driver might set the following flag bit in <b>Flags</b>:





#### WMIREG_FLAG_INSTANCE_PDO

Requests WMI to generate static instance names from the device instance ID for the PDO. If this flag is set, the <i>Pdo</i> parameter of the driver's <i>DpWmiQueryReginfo</i> routine points to the PDO passed to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff540521">AddDevice</a> routine. WMI generates instance names from the device instance path of the PDO. Using the device instance path as a base for static instance names is efficient because such names are guaranteed to be unique. WMI automatically supplies a "friendly" name for the instance as an item in a data block that can be queried by data consumers.

A driver might also set one or more of the following flag bits:





#### WMIREG_FLAG_EVENT_ONLY_GUID

The block can be enabled or disabled as an event only, and cannot be queried or set. If this flag is clear, the block can also be queried or set.



#### WMIREG_FLAG_EXPENSIVE

Requests WMI to send an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550857">IRP_MN_ENABLE_COLLECTION</a> request the first time a data consumer opens the data block and an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550848">IRP_MN_DISABLE_COLLECTION</a> request when the last data consumer closes the data block. This is recommended if collecting such data affects performance, because a driver need not collect the data until a data consumer explicitly requests it by opening the block.



#### WMIREG_FLAG_REMOVE_GUID

Requests WMI to remove support for this block. This flag is valid only in response to a request to update registration information (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a> with <b>Parameters.WMI.DataPath </b>set to WMIUPDATE).


## -remarks



A driver that handles WMI IRPs by calling WMI library support routines builds an array of <b>WMIGUIDREGINFO</b> structures, one for each data block and event block to be registered. The driver sets the <b>GuidList</b> member of its <a href="https://msdn.microsoft.com/library/windows/hardware/ff565813">WMILIB_CONTEXT</a> structure to point to the first <b>WMIGUIDREGINFO</b> in the series.

Memory for this structure can be allocated from paged pool.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544097">DpWmiQueryReginfo</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550848">IRP_MN_DISABLE_COLLECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550857">IRP_MN_ENABLE_COLLECTION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565813">WMILIB_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565807">WmiFireEvent</a>
 

 

