---
UID: NE:wdfobject._WDF_EXECUTION_LEVEL
title: "_WDF_EXECUTION_LEVEL"
author: windows-driver-content
description: The WDF_EXECUTION_LEVEL enumeration type specifies the maximum IRQL at which the framework will call the event callback functions that a driver has supplied for a framework object.
old-location: wdf\wdf_execution_level.htm
old-project: wdf
ms.assetid: 82b1fe8e-054c-4710-9a32-d620a62a070e
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_EXECUTION_LEVEL enumeration, wdf.wdf_execution_level, WdfExecutionLevelInheritFromParent, kmdf.wdf_execution_level, wdfobject/WdfExecutionLevelInvalid, DFGenObjectRef_f9a9ae20-9dba-4c23-910b-04c60e1f9539.xml, wdfobject/WdfExecutionLevelDispatch, WdfExecutionLevelInvalid, wdfobject/WdfExecutionLevelPassive, _WDF_EXECUTION_LEVEL, WdfExecutionLevelPassive, wdfobject/WdfExecutionLevelInheritFromParent, wdfobject/WDF_EXECUTION_LEVEL, WdfExecutionLevelDispatch, WDF_EXECUTION_LEVEL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfobject.h
apiname:
-	WDF_EXECUTION_LEVEL
product: Windows
targetos: Windows
req.typenames: WDF_EXECUTION_LEVEL
req.product: Windows 10 or later.
---

# _WDF_EXECUTION_LEVEL enumeration


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The WDF_EXECUTION_LEVEL enumeration type specifies the maximum IRQL at which the framework will call the event callback functions that a driver has supplied for a framework object.


## -syntax


````
typedef enum _WDF_EXECUTION_LEVEL { 
  WdfExecutionLevelInvalid            = 0x00,
  WdfExecutionLevelInheritFromParent  = 0x1,
  WdfExecutionLevelPassive            = 0x2,
  WdfExecutionLevelDispatch           = 0x3
} WDF_EXECUTION_LEVEL;
````


## -enum-fields




### -field WdfExecutionLevelInvalid

Reserved for system use.


### -field WdfExecutionLevelInheritFromParent

The framework uses the maximum IRQL value of the object's parent, unless the object is one that requires IRQL = DISPATCH_LEVEL (such as a DPC object). This value is the default if a driver does not specify a WDF_EXECUTION_LEVEL-typed value.


### -field WdfExecutionLevelPassive

The framework always calls the object's callback functions at IRQL = PASSIVE_LEVEL.


### -field WdfExecutionLevelDispatch

The framework calls the object's callback functions at IRQL &lt;= DISPATCH_LEVEL. Not available in UMDF.


## -remarks



Drivers use the WDF_EXECUTION_LEVEL enumeration type to specify the <b>ExecutionLevel</b> member of an object's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure.

You can specify an <b>ExecutionLevel</b> value for the following objects:

<ul>
<li>
Framework driver objects

</li>
<li>
Framework device objects

</li>
<li>
Framework file objects

</li>
<li>
Framework general objects

</li>
<li>
Framework queue objects (Framework versions 1.9 and later)

</li>
<li>
Framework timer objects (Framework versions 1.9 and later)

</li>
</ul>
<b>KMDF </b>By default, the framework sets the <b>ExecutionLevel</b> value of framework driver objects to <b>WdfExecutionLevelDispatch.</b>

<b>UMDF </b>By default, the framework sets the <b>ExecutionLevel</b> value of framework driver objects to <b>WdfExecutionLevelPassive.</b>

The default <b>ExecutionLevel</b> value for all other objects is <b>WdfExecutionLevelInheritFromParent.</b>

For more information about execution levels for event callback functions, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/synchronization-techniques-for-wdf-drivers">Synchronization Techniques for Framework-Based Drivers</a>.




## -see-also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_EXECUTION_LEVEL enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

