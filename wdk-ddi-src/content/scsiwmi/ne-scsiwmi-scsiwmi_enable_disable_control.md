---
UID: NE:scsiwmi.SCSIWMI_ENABLE_DISABLE_CONTROL
title: SCSIWMI_ENABLE_DISABLE_CONTROL
author: windows-driver-content
description: The SCSIWMI_ENABLE_DISABLE_CONTROL enumerator is used to specify what to enable or disable.
old-location: storage\scsiwmi_enable_disable_control.htm
old-project: storage
ms.assetid: 0327bdc0-e4a4-4c2f-a9b9-5854e3330068
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: scsiwmi/SCSIWMI_ENABLE_DISABLE_CONTROL, SCSIWMI_ENABLE_DISABLE_CONTROL, ScsiWmiEventControl, storage.scsiwmi_enable_disable_control, scsiwmi/ScsiWmiDataBlockControl, structs-scsibus_58a70c92-6ee7-4385-b212-45672a12ac8b.xml, ScsiWmiDataBlockControl, SCSIWMI_ENABLE_DISABLE_CONTROL enumeration [Storage Devices], scsiwmi/ScsiWmiEventControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	SCSIWMI_ENABLE_DISABLE_CONTROL
product: Windows
targetos: Windows
req.typenames: SCSIWMI_ENABLE_DISABLE_CONTROL
req.product: Windows 10 or later.
---

# SCSIWMI_ENABLE_DISABLE_CONTROL enumeration


## -description


The SCSIWMI_ENABLE_DISABLE_CONTROL enumerator is used to specify what to enable or disable. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -syntax


````
typedef enum  { 
  ScsiWmiEventControl      = 0,
  ScsiWmiDataBlockControl  = 1
} SCSIWMI_ENABLE_DISABLE_CONTROL;
````


## -enum-fields




### -field ScsiWmiEventControl

Indicates that a WMI event is to be enabled or disabled. 


### -field ScsiWmiDataBlockControl

Indicates that a data collection for a block is to be enabled or disabled.  


## -see-also

<a href="..\wmilib\nc-wmilib-wmi_function_control_callback.md">DpWmiFunctionControl</a>



<a href="..\scsiwmi\nc-scsiwmi-pscsiwmi_function_control.md">HwScsiWmiFunctionControl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSIWMI_ENABLE_DISABLE_CONTROL enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

