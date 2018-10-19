---
UID: NF:portcls.IPinCount.PinCount
title: IPinCount::PinCount
author: windows-driver-content
description: The PinCount method queries the miniport driver for its pin count.
old-location: audio\ipincount_pincount.htm
tech.root: audio
ms.assetid: 8b7a49cc-5061-475b-ac03-cbf43954c413
ms.date: 05/08/2018
ms.keywords: IPinCount interface [Audio Devices],PinCount method, IPinCount.PinCount, IPinCount::PinCount, PinCount, PinCount method [Audio Devices], PinCount method [Audio Devices],IPinCount interface, audio.ipincount_pincount, audmp-routines_bded3ce8-936c-4391-901f-df6b2061c7c3.xml, portcls/IPinCount::PinCount
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IPinCount.PinCount
product:
- Windows
targetos: Windows
req.typenames: 
---

# IPinCount::PinCount


## -description


The <code>PinCount</code> method queries the miniport driver for its pin count.


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

During the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a> call, the port driver calls the miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a> method to obtain a pointer to the filter descriptor, which includes the miniport driver's pin-descriptor array (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff537721">PCPIN_DESCRIPTOR</a>). Thereafter, the port driver accesses the pin descriptors to respond to queries for pin properties.

If the miniport driver supports the <b>IPinCount</b> interface, the port driver calls <code>PinCount</code> to give the miniport driver an opportunity to update the pin counts before replying to a pin-property request. If the miniport driver does not support <b>IPinCount</b>, the port driver simply uses the static pin-count limits in the pin-descriptor array.

The port driver calls the <code>PinCount</code> method when it receives one of the following KS property requests:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff565193">KSPROPERTY_PIN_CINSTANCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565200">KSPROPERTY_PIN_GLOBALCINSTANCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565204">KSPROPERTY_PIN_NECESSARYINSTANCES</a>


PortCls also calls the <code>PinCount</code> method each time a new stream is created.

Miniport drivers must not explicitly cause streams to be created or destroyed from within the <code>PinCount</code> method. Miniport drivers are not otherwise restricted in what they can do during this call.

The <code>PinCount</code> method is called at IRQL PASSIVE_LEVEL. The code for this method must reside in paged memory.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536765">IMiniport::GetDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536832">IPinCount</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536943">IPort::Init</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565193">KSPROPERTY_PIN_CINSTANCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565200">KSPROPERTY_PIN_GLOBALCINSTANCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565204">KSPROPERTY_PIN_NECESSARYINSTANCES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537721">PCPIN_DESCRIPTOR</a>
 

 

