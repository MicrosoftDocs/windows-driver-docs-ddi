---
UID: NE:wdfdevice._WDF_FILEOBJECT_CLASS
title: "_WDF_FILEOBJECT_CLASS"
author: windows-driver-content
description: The WDF_FILEOBJECT_CLASS enumeration defines values that identify whether a driver requires a framework file object to represent a file that an application or another driver is attempting to create or open.
old-location: wdf\wdf_fileobject_class.htm
old-project: wdf
ms.assetid: e0887061-eafe-4dba-bb7a-58bf949e2d08
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_FILEOBJECT_CLASS, DFFileObjectRef_001acbc3-7e2c-4b8b-ab14-024653cefe19.xml, PWDF_FILEOBJECT_CLASS, PWDF_FILEOBJECT_CLASS enumeration pointer, WDF_FILEOBJECT_CLASS, WDF_FILEOBJECT_CLASS enumeration, WdfFileObjectCanBeOptional, WdfFileObjectInvalid, WdfFileObjectNotRequired, WdfFileObjectWdfCanUseFsContext, WdfFileObjectWdfCanUseFsContext2, WdfFileObjectWdfCannotUseFsContexts, _WDF_FILEOBJECT_CLASS, kmdf.wdf_fileobject_class, wdf.wdf_fileobject_class, wdfdevice/PWDF_FILEOBJECT_CLASS, wdfdevice/WDF_FILEOBJECT_CLASS, wdfdevice/WdfFileObjectCanBeOptional, wdfdevice/WdfFileObjectInvalid, wdfdevice/WdfFileObjectNotRequired, wdfdevice/WdfFileObjectWdfCanUseFsContext, wdfdevice/WdfFileObjectWdfCanUseFsContext2, wdfdevice/WdfFileObjectWdfCannotUseFsContexts"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_FILEOBJECT_CLASS
product:
- Windows
targetos: Windows
req.typenames: WDF_FILEOBJECT_CLASS, *PWDF_FILEOBJECT_CLASS
req.product: Windows 10 or later.
---

# _WDF_FILEOBJECT_CLASS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_FILEOBJECT_CLASS</b> enumeration defines values that identify whether a driver requires a framework file object to represent a file that an application or another driver is attempting to create or open. These values also specify where the framework can store the object's handle.


## -enum-fields




### -field WdfFileObjectInvalid

Reserved for internal use.


### -field WdfFileObjectNotRequired

The driver does not require a framework file object.


### -field WdfFileObjectWdfCanUseFsContext

The driver requires a framework file object. The framework can store the object's handle in the <b>FsContext</b> member of the file's Windows Driver Model (WDM) <a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a> structure.


### -field WdfFileObjectWdfCanUseFsContext2

The driver requires a framework file object. The framework can store the object's handle in the <b>FsContext2</b> member of the file's WDM FILE_OBJECT structure.


### -field WdfFileObjectWdfCannotUseFsContexts

The driver requires a framework file object. The framework cannot store the object's handle in the <b>FsContext</b> or <b>FsContext2</b> member of the file's WDM FILE_OBJECT structure, because one or more drivers are using these members. Therefore, the framework must store the handle internally.


### -field WdfFileObjectCanBeOptional

The driver typically requires a framework file object, but the driver can also handle special situations in which a framework file object is missing or different. For more information about these situations, see the following Remarks section. 

<b>WdfFileObjectCanBeOptional</b> is a bit flag that your driver can OR with the <b>WdfFileObjectWdfCanUseFsContext</b>, <b>WdfFileObjectWdfCanUseFsContext2</b>, or <b>WdfFileObjectWdfCannotUseFsContexts</b> enumerator value. 

Most framework-based drivers do not use this bit flag.

The <b>WdfFileObjectCanBeOptional</b> value is available in version 1.9 and later versions of KMDF.


## -remarks



The <b>WDF_FILEOBJECT_CLASS</b> enumeration is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551319">WDF_FILEOBJECT_CONFIG</a> structure.

If your driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549963">WdfRequestGetFileObject</a> to obtain framework file objects for I/O requests, and if you know that some of the WDM I/O request packets (IRPs) that your driver receives do not include WDM file objects, the driver can set the <b>WdfFileObjectCanBeOptional</b> bit flag. 

If your driver sets the <b>WdfFileObjectWdfCanUseFsContext</b>, <b>WdfFileObjectWdfCanUseFsContext2</b>, or <b>WdfFileObjectWdfCannotUseFsContexts</b> value and does <i>not</i> set the <b>WdfFileObjectCanBeOptional</b> bit flag, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-kmdf-verifier">the framework's verifier</a> reports an error for the following cases when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549963">WdfRequestGetFileObject</a> method: 

<ul>
<li>
An IRP does not include a WDM file object.

</li>
<li>
An IRP includes a WDM file object, but the file object is different from the one that the file creation IRP included.

</li>
</ul>
If the <b>WdfFileObjectCanBeOptional</b> bit flag is set, the framework's verifier ignores such cases.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545834">FILE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551319">WDF_FILEOBJECT_CONFIG</a>
 

 

