- [Minimum requirements](#minimum-requirements)
- [Armazenamento](#storage)
- [CPU and memory](#cpu-and-memory)

#### Minimum requirements

We recommend different hardware configurations depending on the number of user licenses for {{ site.data.variables.product.product_location_enterprise }}. If you provision more resources than the minimum requirements, your instance will perform and scale better.

{{ site.data.reusables.enterprise_installation.hardware-rec-table }} For more information about adjusting resources for an existing instance, see "[Increasing storage capacity](/enterprise/admin/installation/increasing-storage-capacity)" and "[Increasing CPU or memory resources](/enterprise/admin/installation/increasing-cpu-or-memory-resources)."

{% if currentVersion == "enterprise-server@2.22" %}

If you enable the beta for {{ site.data.variables.product.prodname_actions }} on your instance, we recommend planning for additional capacity.

- You must configure at least one runner for {{ site.data.variables.product.prodname_actions }} workflows. Para obter mais informações, consulte "[Sobre os executores auto-hospedados](/actions/hosting-your-own-runners/about-self-hosted-runners)."
- You must configure external blob storage. Para obter mais informações, consulte "[Habilitar {{ site.data.variables.product.prodname_actions }} e configurar o armazenamento](/enterprise/admin/github-actions/enabling-github-actions-and-configuring-storage)".

The additional CPU and memory resources you need to provision for your instance depend on the number of workflows your users run concurrently, and the overall levels of activity for users, automations, and integrations.

| Maximum jobs per minute | vCPUs | Memória |
|:----------------------- | -----:| -------:|
| Light testing           |     4 | 30.5 GB |
| 25                      |     8 |   61 GB |
| 35                      |    16 |  122 GB |
| 100                     |    32 |  244 GB |

{% endif %}

#### Armazenamento

We recommend a high-performance SSD with high input/output operations per second (IOPS) and low latency for {{ site.data.variables.product.prodname_ghe_server }}. Workloads are I/O intensive. If you use a bare metal hypervisor, we recommend directly attaching the disk or using a disk from a storage area network (SAN).

Your instance requires a persistent data disk separate from the root disk. Para obter mais informações, consulte "[System overview](/enterprise/admin/guides/installation/system-overview)."

{% if currentVersion ver_gt "enterprise-server@2.21" %}

If you enable the beta of {{ site.data.variables.product.prodname_actions }} in {{ site.data.variables.product.prodname_ghe_server }} 2.22, you'll need to configure external blob storage. Para obter mais informações, consulte "[Habilitar {{ site.data.variables.product.prodname_actions }} e configurar o armazenamento](/enterprise/admin/github-actions/enabling-github-actions-and-configuring-storage)".

{% endif %}

You can resize your instance's root disk by building a new instance or using an existing instance. Para obter mais informações, consulte "[Increasing storage capacity](/enterprise/{{ currentVersion }}/admin/guides/installation/increasing-storage-capacity)."

#### CPU and memory

{{ site.data.variables.product.prodname_ghe_server }} requires more CPU and memory resources depending on levels of activity for users, automations, and integrations.

{{ site.data.reusables.enterprise_installation.increasing-cpus-req }}

{% warning %}

**Warning:** We recommend that users configure webhook events to notify external systems of activity on {{ site.data.variables.product.prodname_ghe_server }}. Automated checks for changes, or _polling_, will negatively impact the performance and scalability of your instance. For more information, see "[About webhooks](/github/extending-github/about-webhooks)."

{% endwarning %}

You can increase your instance's CPU or memory resources. Para obter mais informações, consulte "[Increasing CPU or memory resources](/enterprise/admin/installation/increasing-cpu-or-memory-resources).