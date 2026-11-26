# Research examples

## MRI segmentation

Check the target anatomy or pathology, MRI sequences, labels, and intended dataset. Determine whether the researcher wants pretrained inference or training. Find leading models in comparable primary papers and benchmarks. Explain fit to the available annotations, 2D or 3D inputs, and compute. Ask which model and data to use if unspecified and resolve open split, preprocessing, and evaluation choices.

## fastMRI reconstruction

Study the exact fastMRI dataset and challenge documentation and relevant reconstruction papers. Establish the coil setting, undersampling pattern and acceleration, how aliasing arises in that setup, and how the proposed reconstruction addresses it. Ask about unresolved choices such as the acquisition mask, reference, and evaluation protocol.

## MRI EMI removal

Trace acquisition, fitting, EMI subtraction, and reconstruction independently. A fitting mask does not establish acquisition or reconstruction support. For an agreed zero-filled reconstruction, verify that missing lines remain zero in the actual array entering the inverse FFT. If the source method leaves correction support unclear, ask before implementing.

## Molecular property analysis

Check the property endpoint, units, assay provenance, dataset, and evaluation purpose. Consult original studies and relevant benchmark documentation. Explain the effects of choices such as duplicate handling and random versus scaffold splits. Ask which dataset and protocol to use when unresolved, and verify unclear units or assay definitions before combining records.
