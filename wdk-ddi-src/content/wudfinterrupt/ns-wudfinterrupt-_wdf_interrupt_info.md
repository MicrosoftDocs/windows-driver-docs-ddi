---
UID: NS:wudfinterrupt._WDF_INTERRUPT_INFO
title: _WDF_INTERRUPT_INFO
author: windows-driver-content
description: The WDF_INTERRUPT_INFO structure contains information about a device's interrupt resource.
old-location: wdf\wdf_interrupt_info_umdf.htm
old-project: wdf
ms.assetid: 37B997D1-6F5D-4685-BF46-2C33685C157F
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO, WDF_INTERRUPT_INFO
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
req.alt-api: WDF_INTERRUPT_INFO
req.alt-loc: Wudfinterrupt.h
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
req.typenames: *PWDF_INTERRUPT_INFO, WDF_INTERRUPT_INFO
req.product: Windows 10 or later.
---

# _WDF_INTERRUPT_INFO structure



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


      The <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a> structure contains information about a device's interrupt resource.



## -syntax

````
typedef struct _WDF_INTERRUPT_INFO {
  ULONG                  Size;
  ULONG64                Reserved1;
  KAFFINITY              TargetProcessorSet;
  ULONG                  Reserved2;
  ULONG                  MessageNumber;
  ULONG                  Vector;
  KIRQL                  Irql;
  KINTERRUPT_MODE        Mode;
  WDF_INTERRUPT_POLARITY Polarity;
  BOOLEAN                MessageSignaled;
  UCHAR                  ShareDisposition;
  USHORT                 Group;
} WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO;
````


## -struct-fields

### -field Size

The size, in bytes, of this structure.


### -field Reserved1

This member is reserved for future use. 


### -field TargetProcessorSet

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>-typed value that specifies the interrupt's processor affinity.


### -field Reserved2

This member is reserved for future use. 


### -field MessageNumber

If the <b>MessageSignaled</b> member is TRUE, this is the interrupt's message number.


### -field Vector

The interrupt vector.


### -field Irql

The DIRQL at which the device interrupts.


### -field Mode

A <a href="..\wdm\ne-wdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a>-typed enumerator that indicates whether the interrupt is level-triggered or edge-triggered. The KINTERRUPT_MODE enumeration type is defined in Wudfwdm.h.


### -field Polarity

A <a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_polarity.md">WDF_INTERRUPT_POLARITY</a>-typed enumerator that identifies the interrupt signal's polarity.


### -field MessageSignaled

A Boolean value that, if TRUE, indicates that the interrupt is message-signaled. If FALSE, the interrupt is not message-signaled.


### -field ShareDisposition

A CM_SHARE_DISPOSITION-typed enumerator that indicates whether the interrupt is being shared. The value is <b>CmResourceShareShared</b> if the interrupt is being shared or <b>CmResourceShareDeviceExclusive</b> if the interrupt is not being shared. The CM_SHARE_DISPOSITION enumeration type is defined in Wudfwdm.h.


### -field Group

A value that identifies the processor group that the <b>TargetProcessorSet</b> member applies to. This value is zero if the computer has only one processor group or if the operating system does not support processor groups. The <b>Group</b> member is available in version 1.9 and later versions of KMDF.


## -remarks
The <a href="..\wudfinterrupt\ns-wudfinterrupt-_wdf_interrupt_info.md">WDF_INTERRUPT_INFO</a> structure is used as input to the <a href="https://msdn.microsoft.com/744D0FFE-6D3C-4AED-8935-63EE9B0AFA0F">IWDFInterrupt::GetInfo</a> method. To initialize a <b>WDF_INTERRUPT_INFO</b> structure, your driver should call <a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_info_init.md">WDF_INTERRUPT_INFO_INIT</a> before calling <b>IWDFInterrupt::GetInfo</b>.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/744D0FFE-6D3C-4AED-8935-63EE9B0AFA0F">IWDFInterrupt::GetInfo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551830">KAFFINITY</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_kinterrupt_mode.md">KINTERRUPT_MODE</a>
</dt>
<dt>
<a href="..\wudfinterrupt\nf-wudfinterrupt-wdf_interrupt_info_init.md">WDF_INTERRUPT_INFO_INIT</a>
</dt>
<dt>
<a href="..\wudfinterrupt\ne-wudfinterrupt-_wdf_interrupt_polarity.md">WDF_INTERRUPT_POLARITY</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_INTERRUPT_INFO structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

