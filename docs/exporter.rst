Exporter
========

The exporter translates the compiled SystemRDL object model into an IP-XACT XML
document.

The exporter will translate a given AddrmapNode object into an IP-XACT
<component> that contains a single <memoryMap> with one or more <addressBlock>
elements.

Depending on the structure of the design hierarchy, the exporter may attempt to
flatten the design into multiple <addressBlock> elements in order avoid excessive
nesting and make better use of IP-XACT structuring.



Limitations
-----------

Unfortunately, not all SystemRDL concepts are able to be faithfully translated
into IP-XACT.

* SystemRDL describes a vast amount of properties that have no equivalents in
  the IP-XACT standard, so unfortunately they are discarded.
* IP-XACT is not capable of describing memories that are deeply nested in a
  design. Any ``mem`` components that are not immediate children of the top node
  being exported will be discarded.


API
---

.. autoclass:: peakrdl_ipxact.IPXACTExporter
    :special-members: __init__
    :members: export

.. autoclass:: peakrdl_ipxact.Standard
    :members:
