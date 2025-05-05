from pathlib import Path
import nbformat
notebook_path = Path("/mnt/data/Untitled.ipynb")
with notebook_path.open() as f:
    notebook = nbformat.read(f, as_version=4)
notebook_cells = notebook.cells
text_content = []

    if cell.cell_type == "markdown":
        text_content.append(cell.source)
    elif cell.cell_type == "code":
        text_content.append("# Code Cell\n" + cell.source)


combined_text = "\n\n".join(text_content)
combined_text[:1500]  # Display a preview to prepare README content
