---
UID: NS:wdfobject._WDF_OBJECT_CONTEXT_TYPE_INFO
title: "_WDF_OBJECT_CONTEXT_TYPE_INFO"
author: windows-driver-content
description: The WDF_OBJECT_CONTEXT_TYPE_INFO structure describes a framework object's driver-defined context memory.
old-location: wdf\wdf_object_context_type_info.htm
old-project: wdf
ms.assetid: 2b56183e-03aa-493a-84ba-03f9bc5daee2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfobject/WDF_OBJECT_CONTEXT_TYPE_INFO, DFGenObjectRef_8c3ba75b-eb62-455f-a905-61b715478b5b.xml, kmdf.wdf_object_context_type_info, PWDF_OBJECT_CONTEXT_TYPE_INFO, wdf.wdf_object_context_type_info, wdfobject/PWDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO structure, WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO, _WDF_OBJECT_CONTEXT_TYPE_INFO, PWDF_OBJECT_CONTEXT_TYPE_INFO structure pointer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfobject.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfobject.h
apiname:
-	WDF_OBJECT_CONTEXT_TYPE_INFO
product: Windows
targetos: Windows
req.typenames: "*PWDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO"
req.product: Windows 10 or later.
---

# _WDF_OBJECT_CONTEXT_TYPE_INFO structure


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_OBJECT_CONTEXT_TYPE_INFO structure describes a framework object's driver-defined context memory.


## -syntax


````
typedef struct _WDF_OBJECT_CONTEXT_TYPE_INFO {
  ULONG                          Size;
  PCHAR                          ContextName;
  size_t                         ContextSize;
  PCWDF_OBJECT_CONTEXT_TYPE_INFO UniqueType;
  PFN_GET_UNIQUE_CONTEXT_TYPE    EvtDriverGetUniqueContextType;
} WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field ContextName

A quoted string that represents the name of a driver-defined structure that contains an object's context information.


### -field ContextSize

The size, in bytes, of the structure that the <b>ContextName</b> member specifies. The framework allocates space for this structure when it creates an object. If the <b>ContextSizeOverride</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure is nonzero, its value overrides the value in the <b>ContextSize</b> member.


### -field UniqueType

For internal use.


### -field EvtDriverGetUniqueContextType

For internal use.


## -remarks


For each object instance, the framework allocates context memory with a size that is based on the value of the <b>ContextSize</b> member or the value of the <b>ContextSizeOverride</b> member of the <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure.

To create and initialize a WDF_OBJECT_CONTEXT_TYPE_INFO structure, drivers should use either the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551250">WDF_DECLARE_CONTEXT_TYPE</a> macro or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551252">WDF_DECLARE_CONTEXT_TYPE_WITH_NAME</a> macro.

To insert a pointer to this structure into a WDF_OBJECT_ATTRIBUTES structure, drivers should use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552405">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a> macro.

For more information about using these macros, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-context-space">Framework Object Context Space</a>.



## -see-also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551250">WDF_DECLARE_CONTEXT_TYPE</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551252">WDF_DECLARE_CONTEXT_TYPE_WITH_NAME</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552405">WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_OBJECT_CONTEXT_TYPE_INFO structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

