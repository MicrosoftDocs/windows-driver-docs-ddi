---
UID: NS:wmistr.WMIREGINFOW
title: WMIREGINFOW
author: windows-driver-content
description: The WMIREGINFO structure contains information provided by a driver to register or update its data blocks and event blocks.
old-location: kernel\wmireginfo.htm
old-project: kernel
ms.assetid: 7331b30f-f61c-445c-ac0f-07c887ae92d7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PWMIREGINFOW, WMIREGINFOW, WMIREGINFO, kernel.wmireginfo, kstruct_d_2c5c2f97-d385-4cd6-8b0f-c27d4b21ea11.xml, PWMIREGINFOW structure pointer [Kernel-Mode Driver Architecture], *PWMIREGINFOW, WMIREGINFOW structure [Kernel-Mode Driver Architecture], wmistr/WMIREGINFOW, wmistr/PWMIREGINFOW
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wmistr.h
req.include-header: Wmistr.h
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
-	wmistr.h
apiname:
-	WMIREGINFOW
product: Windows
targetos: Windows
req.typenames: "*PWMIREGINFOW, WMIREGINFOW"
req.product: Windows 10 or later.
---

# WMIREGINFOW structure


## -description


The <b>WMIREGINFO</b> structure contains information provided by a driver to register or update its data blocks and event blocks.


## -syntax


````
typedef struct {
  ULONG       BufferSize;
  ULONG       NextWmiRegInfo;
  ULONG       RegistryPath;
  ULONG       MofResourceName;
  ULONG       GuidCount;
  WMIREGGUIDW WmiRegGuid[];
} WMIREGINFOW, *PWMIREGINFOW;
````


## -struct-fields




### -field BufferSize

Indicates the total size of the WMI registration data associated with this <b>WMIREGINFO</b> structure, calculated as follows: (<b>sizeof</b>(<b>WMIREGINFO</b>) + (<b>GuidCount</b> * <b>sizeof</b>(<b>WMIREGGUID</b>) + <i>additionaldata</i>). Additional data might include items such as the MOF resource name, registry path, and static instance names for blocks.


### -field NextWmiRegInfo

If a driver handles WMI requests on behalf of another driver, as a class driver might on behalf of a miniclass driver, <b>NextWmiRegInfo</b> indicates the offset in bytes from the beginning of this <b>WMIREGINFO</b> to the next <b>WMIREGINFO</b> structure that contains WMI registration information for the other driver. Otherwise, <b>NextWmiRegInfo</b> is zero.


### -field RegistryPath

Indicates the offset in bytes from the beginning of this structure to a counted Unicode string that specifies the registry path passed to the driver's <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine. The string must be aligned on a USHORT boundary. This member should be set only in response to a WMI registration request (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a> with <b>Parameters.WMI.DataPath</b> set to WMIREGISTER).


### -field MofResourceName

Indicates the offset in bytes from the beginning of this structure to a counted Unicode string that specifies the name of the MOF resource in the driver's image file. The string must be aligned on a USHORT boundary. This member should be set only in response to a WMI registration request (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a> with <b>Parameters.WMI.DataPath</b> set to WMIREGISTER).


### -field GuidCount

Indicates the number of <a href="..\wmistr\ns-wmistr-wmiregguidw.md">WMIREGGUID</a> structures in the array at <b>WmiRegGuid</b>.


### -field WmiRegGuid

Is an array of <b>GuidCount </b><a href="..\wmistr\ns-wmistr-wmiregguidw.md">WMIREGGUID</a> structures.


## -remarks



In response to a registration request (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a> with <b>Parameters.WMI.DataPath </b>set to WMIREGISTER), a driver builds at least one <b>WMIREGINFO</b> structure and writes the <b>WMIREGINFO</b> structure to the buffer at <b>IrpStack-&gt;Parameters.WMI.Buffer</b>. The <b>WMIREGINFO</b> structure contains an array of <b>WMIREGGUID</b> structures, one for each data block or event block exposed by the driver.

If the driver handles WMI requests on behalf of another driver, it builds another <b>WMIREGINFO</b> containing an array of <b>WMIREGGUID</b> structures for each block exposed by the other driver, sets the <b>NextWmiRegInfo</b> member of the first <b>WMIREGINFO</b> to an offset in bytes from the beginning of the first <b>WMIREGINFO</b> to the beginning of the next <b>WMIREGINFO</b> in the buffer, and writes both structures to the buffer. The driver indicates the total size of both <b>WMIREGINFO</b> structures and associated data when calls <b>IoCompleteRequest</b> to complete the IRP.

A driver can use the same <b>WMIREGINFO</b> structure(s) to remove or update blocks in response to an update request (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a> with <b>Parameters.WMI.DataPath</b> set to WMIUPDATE). If WMIREG_FLAG_REMOVE_GUID is set in the <b>Flags</b> member of a <b>WMIREGGUID</b>, WMI removes that block from the list of blocks previously registered by the driver. If WMIREG_FLAG_REMOVE_GUID is clear, WMI updates registration information for that block only if other <b>WMIREGGUID</b> members have changed—otherwise, WMI does not change to its registration information for that block.




## -see-also

<a href="..\wmistr\ns-wmistr-wmiregguidw.md">WMIREGGUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551731">IRP_MN_REGINFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551734">IRP_MN_REGINFO_EX</a>



<a href="..\wdm\nf-wdm-iocompleterequest.md">IoCompleteRequest</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WMIREGINFOW structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

