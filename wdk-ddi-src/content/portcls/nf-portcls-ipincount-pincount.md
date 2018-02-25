---
UID: NF:portcls.IPinCount.PinCount
title: IPinCount::PinCount method
author: windows-driver-content
description: The PinCount method queries the miniport driver for its pin count.
old-location: audio\ipincount_pincount.htm
old-project: audio
ms.assetid: 8b7a49cc-5061-475b-ac03-cbf43954c413
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, C, I, IPinCount, IPinCount interface [Audio Devices], PinCount method, IPinCount::PinCount, P, PinCount method [Audio Devices], PinCount method [Audio Devices], IPinCount interface, PinCount,IPinCount.PinCount, audio.ipincount_pincount, audmp-routines_bded3ce8-936c-4391-901f-df6b2061c7c3.xml, i, n, o, portcls/IPinCount::PinCount, t, u"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.lib: portcls.h
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	portcls.h
apiname:
-	IPinCount.PinCount
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---

# IPinCount::PinCount method


## -description


The <code>PinCount</code> method queries the miniport driver for its pin count.


## -syntax


````
void PinCount(
  [in]      ULONG  PinId,
  [in, out] PULONG FilterNecessary,
  [in, out] PULONG FilterCurrent,
  [in, out] PULONG FilterPossible,
  [in, out] PULONG GlobalCurrent,
  [in, out] PULONG GlobalPossible
);
````


## -parameters




### -param PinId [in]

Specifies the pin ID. If a filter contains <i>n</i> pin factories, valid pin IDs range from 0 to <i>n</i>-1.


### -param FilterNecessary [in, out]

Specifies the minimum number of pins that the pin factory should instantiate before the filter can perform I/O operations.


### -param FilterCurrent [in, out]

Specifies the current number of pin instances. This number counts the pins that the pin factory has already instantiated on the filter.


### -param FilterPossible [in, out]

Specifies the maximum number of pins that the pin factory can instantiate on the filter. Set to KSINSTANCE_INDETERMINATE if there is no maximum.


### -param GlobalCurrent [in, out]

Specifies the current number of pins that the pin factory has instantiated on the driver.


### -param GlobalPossible [in, out]

Specifies the maximum number of pins that the pin factory can instantiate on the driver. Set to KSINSTANCE_INDETERMINATE if there is no maximum.


## -returns



None




## -remarks



The <code>PinCount</code> call has two purposes:

<ul>
<li>
To let the miniport driver know the current pin counts.

</li>
<li>
To give the miniport driver an opportunity to alter the current pin counts.

</li>
</ul>
<i>FilterNecessary</i>, <i>FilterCurrent</i>, <i>FilterPossible</i>, <i>GlobalCurrent</i>, and <i>GlobalPossible</i> are all IN+OUT parameters that point to values in the miniport driver's filter description. During the <i>PinCount</i> call, the miniport driver can examine these values and has the option of editing the values in order to more accurately indicate how many additional pins can be created from the remaining resources.

<i>FilterCurrent</i> and <i>FilterPossible</i> specify the per-filter values for the pin factory specified by <i>PinId</i>.

<i>GlobalCurrent</i> and <i>GlobalPossible</i> specify the total values for the pin factory over all instances of the filter.

Miniport drivers typically do not need to change the <i>FilterNecessary</i> parameter, but it is included for the sake of completeness.

During the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> call, the port driver calls the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method to obtain a pointer to the filter descriptor, which includes the miniport driver's pin-descriptor array (see <a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_7.md">PCPIN_DESCRIPTOR</a>). Thereafter, the port driver accesses the pin descriptors to respond to queries for pin properties.

If the miniport driver supports the <b>IPinCount</b> interface, the port driver calls <code>PinCount</code> to give the miniport driver an opportunity to update the pin counts before replying to a pin-property request. If the miniport driver does not support <b>IPinCount</b>, the port driver simply uses the static pin-count limits in the pin-descriptor array.

The port driver calls the <code>PinCount</code> method when it receives one of the following KS property requests:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff565193">KSPROPERTY_PIN_CINSTANCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565200">KSPROPERTY_PIN_GLOBALCINSTANCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565204">KSPROPERTY_PIN_NECESSARYINSTANCES</a>


PortCls also calls the <code>PinCount</code> method each time a new stream is created.

Miniport drivers must not explicitly cause streams to be created or destroyed from within the <code>PinCount</code> method. Miniport drivers are not otherwise restricted in what they can do during this call.

The <code>PinCount</code> method is called at IRQL PASSIVE_LEVEL. The code for this method must reside in paged memory.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>



<a href="..\portcls\ns-portcls-__unnamed_struct_0cb6_7.md">PCPIN_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565200">KSPROPERTY_PIN_GLOBALCINSTANCES</a>



<a href="..\portcls\nn-portcls-ipincount.md">IPinCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565193">KSPROPERTY_PIN_CINSTANCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565204">KSPROPERTY_PIN_NECESSARYINSTANCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPinCount::PinCount method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

