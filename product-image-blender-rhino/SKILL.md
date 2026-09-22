---
name: product-image-blender-rhino
description: Build product or furniture models from reference and dimension images in Blender, transfer them to Rhino, and deliver validated 3DM, BLEND, OBJ/MTL, scripts, and model notes. Use when a request involves image-based product reconstruction, Blender-to-Rhino conversion, or a verified Rhino mesh deliverable.
---

# Product Image to Blender and Rhino

Turn product photos and dimension drawings into an editable Blender model and a verified Rhino `.3dm` deliverable. Complete the files rather than stopping at instructions.

## Route the work

Read [references/workflow.md](references/workflow.md) before starting. It contains the required modeling, transfer, validation, and delivery workflow.

Extract the input folder, output folder, model name, dimensions, and requested deliverables from the user's request. If a value is missing, infer safe defaults from the current workspace and filenames when possible. Ask only when the missing value would materially change the result.

Use available Blender and Rhino MCP tools. If the environment supports subagents and the user has authorized delegation, the main agent owns image interpretation, Blender modeling, visual review, integration, and independent final validation; assign the export/import stage to Luna (`gpt-5.6-luna`) when that exact model is available. Never claim Luna or an MCP was used when it was unavailable. Continue all work that does not depend on a missing tool and report the precise blocker.

## Preserve the user's work

- Inspect the current Blender scene and Rhino documents before changing them.
- Put the new model in a dedicated collection and Rhino layer named for the model.
- Do not delete unrelated objects, clear scenes, close unsaved documents, or overwrite source images.
- If an output filename exists, create a versioned filename unless the user explicitly requested replacement.
- Avoid concurrent edits to the same Blender scene or Rhino document.

## Required outcome

Use dimension drawings as the primary source and photographs for shape, construction, proportion, and detail. Mark inferred dimensions as estimates. Model in meters in Blender and deliver Rhino geometry in millimeters, applying the scale conversion exactly once.

Keep meaningful parts separate with stable names and basic material assignments. Retain a reproducible modeling script and update it for final fixes.

Do not declare completion until the saved `.3dm` has been independently read back and checked for units, dimensions, object count, mesh validity, names, layers, materials, and assignments. A visible Rhino viewport or a subagent completion message is not sufficient evidence.

## Deliverables

Unless the user narrows the request, produce:

- `<model>.3dm`
- `<model>.blend`
- `<model>.obj` and `<model>.mtl`
- the reproducible modeling script
- `MODEL_NOTES.md`

In the final response, link the `.3dm` and `.blend`, report valid object count and measured dimensions, identify estimated details, and state that the Rhino result is a reconstructed mesh rather than original manufacturing NURBS/CAD.
