---
UID: NS:1394._SET_LOCAL_HOST_PROPS3
title: "_SET_LOCAL_HOST_PROPS3"
author: windows-driver-content
description: SET_LOCAL_HOST_PROPS3 contains the data necessary for defining or identifying one or more unit directories in the Configuration ROM of a 1394 Host Controller.
old-location: ieee\set_local_host_props3.htm
old-project: IEEE
ms.assetid: f49a8b86-5611-4737-9b25-e7446e155bbc
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: 1394/PSET_LOCAL_HOST_PROPS3, PSET_LOCAL_HOST_PROPS3, PSET_LOCAL_HOST_PROPS3 structure pointer [Buses], IEEE.set_local_host_props3, SET_LOCAL_HOST_PROPS3 structure [Buses], 1394/SET_LOCAL_HOST_PROPS3, _SET_LOCAL_HOST_PROPS3, *PSET_LOCAL_HOST_PROPS3, SET_LOCAL_HOST_PROPS3, 1394stct_3e1725d2-1109-4762-b64e-05283146250a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 1394.h
req.include-header: 1394.h
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
-	1394.h
apiname:
-	SET_LOCAL_HOST_PROPS3
product: Windows
targetos: Windows
req.typenames: "*PSET_LOCAL_HOST_PROPS3, SET_LOCAL_HOST_PROPS3"
---

# _SET_LOCAL_HOST_PROPS3 structure


## -description


SET_LOCAL_HOST_PROPS3 contains the data necessary for defining or identifying one or more unit directories in the Configuration ROM of a 1394 Host Controller. 


## -syntax


````
typedef struct _SET_LOCAL_HOST_PROPS3 {
  ULONG  fulFlags;
  HANDLE hCromData;
  ULONG  nLength;
  PMDL   Mdl;
} SET_LOCAL_HOST_PROPS3, *PSET_LOCAL_HOST_PROPS3;
````


## -struct-fields




### -field fulFlags

Specifies the action to be taken with the unit directory data contained in the SET_LOCAL_HOST_PROPS3 structure.
<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
SLHP_FLAG_ADD_CROM_DATA

</td>
<td>
Indicates that the data contained in the SET_LOCAL_HOST_PROPS3 structure is to be used to create a new unit directory in the Host Controller's Configuration ROM. 

</td>
</tr>
<tr>
<td>
SLHP_FLAG_REMOVE_CROM_DATA

</td>
<td>
Indicates that the data contained in the SET_LOCAL_HOST_PROPS3 structure is to be used to identify and remove an existing unit directory in the Host Controller's Configuration ROM.  

</td>
</tr>
</table> 


### -field hCromData

Contains a handle that is returned after one or more unit directories have been created. Drivers must store this value and pass it to the bus driver when removing these unit directories. If the SLHP_FLAG_ADD_CROM_DATA flag is set, then this is an output parameter. If the SLHP_FLAG_REMOVE_CROM_DATA flag is set, then this is an input parameter. 


### -field nLength

Contains length of the data buffer pointed to by <b>Mdl</b>.


### -field Mdl

Pointer to the data buffer containing the unit directory information.


## -remarks


The SET_LOCAL_HOST_PROPS3 structure is sent to the bus driver in the <b>u.SetLocalHostProperties.Information</b> member of an IRB during a <a href="https://msdn.microsoft.com/library/windows/hardware/ff537663">REQUEST_SET_LOCAL_HOST_PROPERTIES</a> request, with <b>u.SetLocalHostProperties.nLevel=</b> SET_LOCAL_HOST_PROPERTIES_MODIFY_CROM. 

The first element of the buffer pointed to by <b>Mdl</b> must be a unit directory. This is followed by offsets to any other leafs or directories defined in the request. The offsets must be relative to the beginning of the buffer. If the request results in the creation of a new unit directory, the bus driver adds a pointer to the newly created directory in the root directory. The buffer pointed to by <b>Mdl</b> must be in big-endian data format. If a driver fails to remove its dynamically added Configuration ROM data when the driver is removed, the bus driver does so automatically, restoring the default contents of the Configuration ROM. 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537204">IEEE1394_API_REQUEST</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff537663">REQUEST_SET_LOCAL_HOST_PROPERTIES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20SET_LOCAL_HOST_PROPS3 structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

