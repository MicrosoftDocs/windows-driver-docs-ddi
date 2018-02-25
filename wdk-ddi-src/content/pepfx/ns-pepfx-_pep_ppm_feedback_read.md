---
UID: NS:pepfx._PEP_PPM_FEEDBACK_READ
title: "_PEP_PPM_FEEDBACK_READ"
author: windows-driver-content
description: The PEP_PPM_FEEDBACK_READ structure contains the value read from a processor performance feedback counter.
old-location: kernel\pep_ppm_feedback_read.htm
old-project: kernel
ms.assetid: 9D5787B8-CEF4-49AA-B7C6-C200AC95A280
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *PPEP_PPM_FEEDBACK_READ, ,, A, B, C, D, E, F, K, M, P, PEP_PPM_FEEDBACK_READ, PEP_PPM_FEEDBACK_READ structure [Kernel-Mode Driver Architecture], PPEP_PPM_FEEDBACK_READ, PPEP_PPM_FEEDBACK_READ structure pointer [Kernel-Mode Driver Architecture], R, _, _PEP_PPM_FEEDBACK_READ, kernel.pep_ppm_feedback_read, pepfx/PEP_PPM_FEEDBACK_READ, pepfx/PPEP_PPM_FEEDBACK_READ"
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
-	PEP_PPM_FEEDBACK_READ
product: Windows
targetos: Windows
req.typenames: PEP_PPM_FEEDBACK_READ, *PPEP_PPM_FEEDBACK_READ
---

# _PEP_PPM_FEEDBACK_READ structure


## -description


The <b>PEP_PPM_FEEDBACK_READ</b> structure contains the value read from a processor performance feedback counter.


## -syntax


````
typedef struct _PEP_PPM_FEEDBACK_READ {
  ULONG CounterIndex;
  union {
    ULONG64 InstantaneousValue;
    struct {
      ULONG64 NominalCount;
      ULONG64 ActualCount;
    };
  };
} PEP_PPM_FEEDBACK_READ, *PPEP_PPM_FEEDBACK_READ;
````


## -struct-fields




### -field CounterIndex

[in] The index that identifies which processor performance feedback counter to read. If the platform extension plug-in (PEP) supports N counters for this processor, counter indexes range from 0 to N-1. The PEP previously supplied the number of supported counters in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186820">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a> notification.


### -field NominalCount

 


### -field ActualCount

 




#### - ( unnamed union )

Either an instantaneous counter value, if the counter generates an instantaneous value, or both relative and accumulated counter values, if the counter hardware generates a relative value. For more information, see Remarks.



#### InstantaneousValue

[out] The current instantaneous value read from the counter, if the counter generates an instantaneous value.



#### ( unnamed struct )

The nominal accumulated count and actual count, if the counter hardware generates a relative value.



##### NominalCount

[out] The nominal accumulated value of the counter. The accumulated value is the sum of all actual values that have so far been read from the counter hardware.



##### ActualCount

[out] The actual value read from the counter.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186802">PEP_NOTIFY_PPM_FEEDBACK_READ</a> notification. The <b>CounterIndex</b> member of the structure contains an input value supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is set. The other members contain output values that the PEP writes to the structure in response to the notification. The PEP writes to the <b>InstantaneousValue</b> member if the counter generates an instantaneous value, or to the <b>NominalCount</b> and <b>ActualCount</b> members if the counter generates a relative value.

Both an instantaneous counter and a relative counter are reset to zero when power is first turned on, but reading a relative counter causes the count to reset to zero, whereas reading an instantaneous counter does not reset the count. The PEP previously indicated whether the counter is instantaneous or relative in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186823">PEP_NOTIFY_PPM_QUERY_FEEDBACK_COUNTERS</a> notification.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186820">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186823">PEP_NOTIFY_PPM_QUERY_FEEDBACK_COUNTERS</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186802">PEP_NOTIFY_PPM_FEEDBACK_READ</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_FEEDBACK_READ structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

