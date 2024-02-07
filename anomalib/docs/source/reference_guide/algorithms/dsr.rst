Dsr
------

This is the implementation of the `DSR <https://link.springer.com/chapter/10.1007/978-3-031-19821-2_31>`_ paper.

Model Type: Segmentation

Description
***********

DSR is a quantized-feature based algorithm that consists of an autoencoder with one encoder and two decoders, coupled with an anomaly detection module. DSR learns a codebook of quantized representations on ImageNet, which are then used to encode input images. These quantized representations also serve to sample near-in-distribution anomalies, since they do not rely on external datasets. Training takes place in three phases. The encoder and "general object decoder", as well as the codebook, are pretrained on ImageNet. Defects are then generated at the feature level using the codebook on the quantized representations, and are used to train the object-specific decoder as well as the anomaly detection module. In the final phase of training, the upsampling module is trained on simulated image-level smudges in order to output more robust anomaly maps.

Architecture
************

.. image:: https://raw.githubusercontent.com/openvinotoolkit/anomalib/main/docs/source/images/dsr/architecture.png
    :alt: DSR Architecture

Usage
*****

.. code-block:: bash

    $ python tools/train.py --model dsr


.. automodule:: anomalib.models.dsr.torch_model
   :members:
   :undoc-members:
   :show-inheritance:

.. automodule:: anomalib.models.dsr.lightning_model
   :members:
   :undoc-members:
   :show-inheritance:

.. automodule:: anomalib.models.dsr.anomaly_generator
   :members:
   :undoc-members:
   :show-inheritance:

.. automodule:: anomalib.models.dsr.loss
   :members:
   :undoc-members:
   :show-inheritance:
