Inference Setup
-----------------------
The entrypoint for inference with DeepSpeed is ``deepspeed.init_inference()``.

Example usage:

.. code-block:: python

    engine = deepspeed.init_inference(model=net, config=config)

The ``DeepSpeedInferenceConfig`` is used to control all aspects of initializing
the ``InferenceEngine``. The config should be passed as a dictionary to
``init_inference``, but parameters can also be passed as keyword arguments.

.. _DeepSpeedInferenceConfig:
.. autopydantic_model:: deepspeed.inference.config.DeepSpeedInferenceConfig

Example config:

.. code-block:: python

    config = {
	"kernel_inject": True,
	"tensor_parallel": {"tp_size": 4},
	"dtype": "fp16",
	"enable_cuda_graph": False,
	"replace_method": "auto",
    }

.. autofunction:: deepspeed.init_inference
