---
UID: NS:wudfinterrupt._WUDF_INTERRUPT_CONFIG
title: "_WUDF_INTERRUPT_CONFIG"
author: windows-driver-content
description: The WUDF_INTERRUPT_CONFIG structure contains configuration information for a device interrupt.
old-location: wdf\wudf_interrupt_config.htm
old-project: wdf
ms.assetid: 7A849A10-2C47-42E2-8BEB-E1D979D3C893
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWUDF_INTERRUPT_CONFIG, PWUDF_INTERRUPT_CONFIG, PWUDF_INTERRUPT_CONFIG structure pointer, WUDF_INTERRUPT_CONFIG, WUDF_INTERRUPT_CONFIG structure, _WUDF_INTERRUPT_CONFIG, umdf.wudf_interrupt_config, wdf.wudf_interrupt_config, wudfinterrupt/PWUDF_INTERRUPT_CONFIG, wudfinterrupt/WUDF_INTERRUPT_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfinterrupt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
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
-	Wudfinterrupt.h
api_name:
-	WUDF_INTERRUPT_CONFIG
product: Windows
targetos: Windows
req.typenames: WUDF_INTERRUPT_CONFIG, *PWUDF_INTERRUPT_CONFIG
---

# _WUDF_INTERRUPT_CONFIG structure


## -description


<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


   The <b>WUDF_INTERRUPT_CONFIG</b> structure contains configuration information for a device interrupt.


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field ShareVector

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552533">WDF_TRI_STATE</a>-typed value. If this value is <b>WdfTrue</b>, the interrupt vector can be shared. If the value is <b>WdfFalse</b>, the interrupt vector cannot be shared. If the value is <b>WdfDefault</b> and the interrupt is level-triggered,  the Plug and Play manager uses the bus driver's value. If the value is <b>WdfDefault</b> and the interrupt is not level-triggered, the interrupt vector cannot be shared.


### -field AutomaticSerialization

A Boolean value that, if TRUE, indicates that the framework will synchronize execution of the interrupt object's <a href="https://msdn.microsoft.com/10677BC2-2A98-41C8-BAE9-1FA3689ACD93">OnInterruptWorkItem</a> callback function with other callback functions that use the framework's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/specifying-a-callback-synchronization-mode">callback synchronization</a> functionality.  See  Remarks for more information.


### -field OnInterruptIsr

A pointer to the driver's <a href="https://msdn.microsoft.com/D4B8182A-67A5-4D64-A95C-5EB6A1C1E4F0">OnInterruptIsr</a> callback function, or NULL.


### -field OnInterruptEnable

A pointer to the driver's <a href="https://msdn.microsoft.com/6C091427-59FF-4101-ACD6-353C959794F6">OnInterruptEnable</a> callback function, or NULL.


### -field OnInterruptDisable

A pointer to the driver's <a href="https://msdn.microsoft.com/3ADBD4C2-075E-4988-BF13-EB0C3E0C02BF">OnInterruptDisable</a> callback function, or NULL.


### -field OnInterruptWorkItem

A pointer to the driver's <a href="https://msdn.microsoft.com/10677BC2-2A98-41C8-BAE9-1FA3689ACD93">OnInterruptWorkItem</a> callback function, or NULL.


### -field InterruptRaw

A pointer to the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/raw-and-translated-resources">raw resources</a> that the system assigned to the interrupt. This member is only used if the interrupt is created in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a> callback.


### -field InterruptTranslated

A pointer to the <a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure that describes the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/raw-and-translated-resources">translated resources</a> that the system assigned to the interrupt. This member is only used if the interrupt is created in the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439734">OnPrepareHardware</a> callback.


## -remarks



The <b>WUDF_INTERRUPT_CONFIG</b> structure is used as input to <a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice3::CreateInterrupt</a>.

To initialize a <b>WUDF_INTERRUPT_CONFIG</b> structure, your driver should first call <a href="https://msdn.microsoft.com/library/windows/hardware/hh464089">WUDF_INTERRUPT_CONFIG_INIT</a> and then fill in structure members that <b>WUDF_INTERRUPT_CONFIG_INIT</b> does not initialize.

Before setting <b>AutomaticSerialization</b> to TRUE, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff556991">IWDFDeviceInitialize::SetLockingConstraint</a> with the <i>LockType</i> parameter set to <b>WdfDeviceLevel</b>.

Your driver should include Wudfwdm.h, which contains the definition of CM_PARTIAL_RESOURCE_DESCRIPTOR.


UMDF supports edge-triggered, line-based interrupts and message-signaled interrupts (MSI) on all framework-supported operating systems. Because these types of interrupt resources are not shared, a driver that uses them should set the <b>ShareVector</b> member of this structure to WdfFalse or WdfUseDefault. If the driver specifies an invalid <b>ShareVector</b> value, the driver fails to start.




## -see-also




<a href="https://msdn.microsoft.com/EE68BED8-5FDC-4590-8E95-B228F1DFD32D">IWDFDevice3::CreateInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556991">IWDFDeviceInitialize::SetLockingConstraint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464089">WUDF_INTERRUPT_CONFIG_INIT</a>
 

 

