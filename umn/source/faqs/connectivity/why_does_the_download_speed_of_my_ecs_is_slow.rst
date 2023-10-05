:original_name: faq_connect_180507.html

.. _faq_connect_180507:

Why Does the Download Speed of My ECS Is Slow?
==============================================

If the download speed of an ECS is slow, check the following:

-  Bandwidth limit exceeded: Your used bandwidth exceeds its limit and the limiting policy of the bandwidth takes effect, causing packet loss and slowing down the access. You can check the bandwidth usage or increase the bandwidth.

   If your service traffic continues to be high, you can increase the bandwidth by referring to :ref:`Modifying a Shared Bandwidth <bandwidth_0006>`.

-  The memory usage of the ECS is higher than 80%.

   For details, see section "Why Is My Linux ECS Running Slowly?" or "Why Is My Windows ECS Running Slowly?" in the *Elastic Cloud Server User Guide*.\ `Why Is My Linux ECS Running Slowly? <https://docs.otc.t-systems.com/elastic-cloud-server/umn/faqs/resource_monitoring/why_is_my_linux_ecs_running_slowly.html#en-us-topic-0167429329>`__ or `Why Is My Windows ECS Running Slowly? <https://docs.otc.t-systems.com/elastic-cloud-server/umn/faqs/resource_monitoring/why_is_my_windows_ecs_running_slowly.html#en-us-topic-0167429328>`__

-  Unstable carrier lines: The network between the local server and the cloud is unstable. Contact the carrier to check the network status.
