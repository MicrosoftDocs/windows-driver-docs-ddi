---
UID: NS:wmilib._WMIGUIDREGINFO
title: "_WMIGUIDREGINFO"
author: windows-driver-content
description: The WMIGUIDREGINFO structure contains registration information for a given data block or event block exposed by a driver that uses the WMI library support routines.
old-location: kernel\wmiguidreginfo.htm
old-project: kernel
ms.assetid: 8bf36e54-5caa-4dc6-b659-ea0c1ac450f0
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wmilib.h
apiname:
-	WMIGUIDREGINFO
product: Windows
targetos: Windows
req.typenames: WMIGUIDREGINFO, *PWMIGUIDREGINFO
req.product: Windows 10 or later.
---

# _WMIGUIDREGINFO structure


## -description


The <b>WMIGUIDREGINFO</b> structure contains registration information for a given data block or event block exposed by a driver that uses the WMI library support routines.


## -syntax


````
typedef struct _WMIGUIDREGINFO {
  LPCGUID Guid;
  ULONG   InstanceCount;
  ULONG   Flags;
} WMIGUIDREGINFO, *PWMIGUIDREGINFO;
````


## -struct-fields




### -field Guid

Pointer to the GUID that identifies the block. The memory that contains the GUID can be paged unless it is also used to call <a href="..\wmilib\nf-wmilib-wmifireevent.md">WmiFireEvent</a>.


### -field InstanceCount

Specifies the number of instances defined for the block.


### -field Flags

Flag bits that indicate characteristics of the block. These flag bits are defined in the Wmistr.h header file. WMI ORs the <b>Flags</b> parameter value with the flag bits set by the driver in the <i>RegFlags</i> parameter of its <a href="..\wmilib\nc-wmilib-wmi_query_reginfo_callback.md">DpWmiQueryReginfo</a> routine, which apply to all of the data blocks and event blocks registered by the driver. <b>Flags</b> therefore supplements the driver's default settings for a given block.

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



A driver that handles WMI IRPs by calling WMI library support routines builds an array of <b>WMIGUIDREGINFO</b> structures, one for each data block and event block to be registered. The driver sets the <b>GuidList</b> member of its <a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a> structure to point to the first <b>WMIGUIDREGINFO</b> in the series.

Memory for this structure can be allocated from paged pool.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550857">IRP_MN_ENABLE_COLLECTION</a>



<a href="..\wmilib\nc-wmilib-wmi_query_reginfo_callback.md">DpWmiQueryReginfo</a>



<a href="..\wmilib\ns-wmilib-_wmilib_context.md">WMILIB_CONTEXT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550848">IRP_MN_DISABLE_COLLECTION</a>



<a href="..\wmilib\nf-wmilib-wmifireevent.md">WmiFireEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WMIGUIDREGINFO structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

