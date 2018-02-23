---
UID: NS:pepfx._PEP_PROCESSOR_IDLE_STATE_V2
title: "_PEP_PROCESSOR_IDLE_STATE_V2"
author: windows-driver-content
description: The PEP_PROCESSOR_IDLE_STATE_V2 structure describes a processor idle state that the platform extension plug-in (PEP) supports.
old-location: kernel\pep_processor_idle_state_v2.htm
old-project: kernel
ms.assetid: DEA8B166-5236-4BE3-B16D-9EE1B34796F8
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: pepfx/PEP_PROCESSOR_IDLE_STATE_V2, _PEP_PROCESSOR_IDLE_STATE_V2, kernel.pep_processor_idle_state_v2, pepfx/PPEP_PROCESSOR_IDLE_STATE_V2, PEP_PROCESSOR_IDLE_STATE_V2, *PPEP_PROCESSOR_IDLE_STATE_V2, PPEP_PROCESSOR_IDLE_STATE_V2, PEP_PROCESSOR_IDLE_STATE_V2 structure [Kernel-Mode Driver Architecture], PPEP_PROCESSOR_IDLE_STATE_V2 structure pointer [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PROCESSOR_IDLE_STATE_V2
product: Windows
targetos: Windows
req.typenames: PEP_PROCESSOR_IDLE_STATE_V2, *PPEP_PROCESSOR_IDLE_STATE_V2
---

# _PEP_PROCESSOR_IDLE_STATE_V2 structure


## -description


The <b>PEP_PROCESSOR_IDLE_STATE_V2</b> structure describes a processor idle state that the platform extension plug-in (PEP) supports.


## -syntax


````
typedef struct _PEP_PROCESSOR_IDLE_STATE_V2 {
  union {
    ULONG  Ulong;
    struct {
      ULONG Interruptible  :1;
      ULONG CacheCoherent  :1;
      ULONG ThreadContextRetained  :1;
      ULONG CStateType  :4;
      ULONG WakesSpuriously  :1;
      ULONG PlatformOnly  :1;
      ULONG Autonomous  :1;
      ULONG Reserved  :22;
    };
  };
  ULONG Latency;
  ULONG BreakEvenDuration;
} PEP_PROCESSOR_IDLE_STATE_V2, *PPEP_PROCESSOR_IDLE_STATE_V2;
````


## -struct-fields




### -field Interruptible

 


### -field CacheCoherent

 


### -field ThreadContextRetained

 


### -field CStateType

 


### -field WakesSpuriously

 


### -field PlatformOnly

 


### -field Autonomous

 


### -field Reserved

 


### -field Latency

The worst-case latency, in 100-nanosecond units,  that the processor requires to wake from this idle state in response to a wake event.


### -field BreakEvenDuration

The minimum amount of time, specified in 100-nanosecond units, that the processor must spend in this idle state to make a transition to this state worthwhile. The Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) uses this member value as a hint to avoid switching a processor to an idle state unless the processor is likely to remain in this state for at least the amount of time specified by <b>BreakEvenDuration</b>.


#### - ( unnamed union )

A collection of flag bits and status fields that can be accessed either individually as bitfields, or together as a 32-bit unsigned integer value.



#### Ulong

Flag bits and status fields accessed as a single 32-bit unsigned integer value.



#### ( unnamed struct )

Flag bits and status fields accessed as individual bitfields.



##### Interruptible

Whether the processor can respond to interrupts when in this idle state. Set this flag bit to 1 if the processor can respond to interrupts, and to 0 if it cannot.



##### CacheCoherent

Whether the processor's local cache or caches remain coherent through the duration of this processor idle state. Set this flag bit to 1 if cache coherency is maintained in this idle state, and to 0 if it is not.



##### ThreadContextRetained

Whether thread context is retained in this processor idle state. Set this flag bit to 1 if the processor hardware retains the thread context across the idle transition. Set to 0 if the processor uses the multiprocessor parking protocol to exit the idle state and return control to the operating system. For more information about this protocol, see the document titled "Multiprocessor Startup for ARM Platforms" at <a href="https://www.acpica.org/related-documents">https://www.acpica.org/related-documents</a>.



##### CStateType

The C-state type of the processor idle state. Set this bitfield to zero if this idle state does not correspond to an ACPI-defined C-state. Otherwise, set this bitfield to the C-state number. That is, set <b>CStateType</b> = 1 for C1, set <b>CStateType</b> = 2 for C2, and so on. For more information about C-states, see section 8.1, "Processor Power States", of the Advanced Configuration and Control Specification, Revision 5.0 (<a href="http://www.acpi.info">ACPI 5.0 specification</a>).



##### WakesSpuriously

Whether the processor can wake spuriously in this idle state. Set this flag bit to 0 if the processor is guaranteed to stay in this idle state until it receives a device interrupt, inter-processor interrupt (IPI), or wake request. Set to 1 if the processor might wake autonomously for some other reason.



##### PlatformOnly

Whether the transition to this processor idle state can be performed only as part of a coordinated transition to a platform-wide idle state. Set this flag bit to 1 if the processor idle state transition can be performed only as part of a transition to a platform idle state. Otherwise, set to 0.



##### Autonomous

Whether a coordinated transition to this processor idle state is performed autonomously by the processor hardware. Set this flag bit to 1 if these transitions are autonomous, and to 0 if they are not. A flag value of 1 indicates that the idle state can be entered without sending a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186831">PEP_NOTIFY_PPM_TEST_IDLE_STATE</a>, <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186836">PEP_NOTIFY_PPM_IDLE_PRE_EXECUTE</a>, or <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186803">PEP_NOTIFY_PPM_IDLE_COMPLETE</a> notification. This flag can be set to 1 only if <b>CStateType</b> is nonzero.



##### Reserved

Reserved for future use. Set to zero.


## -remarks



This structure is used in conjunction with the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. The <b>IdleStates</b>  member of the <a href="..\pep_x\ns-pep_x-_pep_ppm_query_coordinated_states.md">PEP_PPM_QUERY_IDLE_STATES_V2</a> structure is the first element in an array of <b>PEP_PROCESSOR_IDLE_STATE_V2</b> structures.




## -see-also

<a href="..\pep_x\ns-pep_x-_pep_ppm_query_coordinated_states.md">PEP_PPM_QUERY_IDLE_STATES_V2</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PROCESSOR_IDLE_STATE_V2 structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

