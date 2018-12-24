---
UID: NE:portabledevice.tagDELETE_OBJECT_OPTIONS
title: tagDELETE_OBJECT_OPTIONS
description: The DELETE_OBJECT_OPTIONS enumeration type describes options that are supported by a device when deleting an object.
old-location: wpddk\delete_object_options.htm
tech.root: wpd_dk
ms.assetid: 38ad1645-1c38-440a-bec2-13052b9082a9
ms.date: 02/15/2018
ms.keywords: DELETE_OBJECT_OPTIONS, DELETE_OBJECT_OPTIONS enumeration, PORTABLE_DEVICE_DELETE_NO_RECURSION, PORTABLE_DEVICE_DELETE_WITH_RECURSION, enumeration, portabledevice/DELETE_OBJECT_OPTIONS, portabledevice/PORTABLE_DEVICE_DELETE_NO_RECURSION, portabledevice/PORTABLE_DEVICE_DELETE_WITH_RECURSION, tagDELETE_OBJECT_OPTIONS, wpddk.delete_object_options
ms.topic: enum
req.header: portabledevice.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	PortableDevice.h
api_name:
-	DELETE_OBJECT_OPTIONS
product:
-	Windows
targetos: Windows
req.typenames: DELETE_OBJECT_OPTIONS
ms.custom: RS5
---

# tagDELETE_OBJECT_OPTIONS enumeration


## -description



The <b>DELETE_OBJECT_OPTIONS</b> enumeration type describes options that are supported by a device when deleting an object.




## -enum-fields




### -field PORTABLE_DEVICE_DELETE_NO_RECURSION

Delete the object only and fail if it has children.


### -field PORTABLE_DEVICE_DELETE_WITH_RECURSION

Delete the object and all its children.


## -remarks



An application can retrieve the deletion options that the device supports by calling the <b>IPortableDeviceCapabilities::GetCommandOptions</b> method for the <b>WPD_COMMAND_OBJECT_MANAGEMENT_DELETE_OBJECTS</b> command. It should examine the <b>WPD_OPTION_OBJECT_MANAGEMENT_RECURSIVE_DELETE_SUPPORTED</b> option value that this method returns in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff597598">IPortableDeviceValuesCollection</a> object.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff597672">Structures and Enumeration Types</a>
 

 

