# Resume Tailor

**Resume Tailor** is a Python tool that automatically tailors your resume to a specific job description using Google Gemini AI, while preserving your original formatting (including bold text and hyperlinks like your GitHub Repository). The tailored resume is saved as a new `.docx` file and can be converted to PDF.

---

## Features

- Reads your original resume (`resume.docx`) and a job description (`job_description.txt`)
- Uses Gemini AI to rewrite each section of your resume to better match the job description
- Preserves formatting such as bold text and hyperlinks (e.g., GitHub Repository)
- Automatically names the output files based on the job role
- Converts the tailored resume to PDF (requires Microsoft Word)

---

## Requirements

- Python 3.7+
- [Google Gemini API key](https://aistudio.google.com/app/apikey)
- Microsoft Word (for PDF conversion)
- Python packages:
  - `docx`
  - `docx2pdf`
  - `google-generativeai`
  - `re`

Install dependencies with:
```bash
pip install python-docx docx2pdf google-generativeai
```

---

## Usage

1. **Prepare your files:**
   - Place your resume as `resume.docx` in the project folder.
   - Place the job description as `job_description.txt` in the same folder.

2. **Set your Gemini API key:**
   - Open `tailor_resume.py`
   - Replace `YOUR_GEMINI_API_KEY` with your actual Gemini API key.

3. **Run the script:**
   ```bash
   python tailor_resume.py
   ```

4. **Output:**
   - The tailored resume will be saved as `tailored_resume_<Role>.docx` and `tailored_resume_<Role>.pdf` (where `<Role>` is extracted from the job description).

---

## Notes

- The script preserves bold formatting and hyperlinks for "GitHub Repository" (and can be extended for other links).
- If the tailored content changes anchor text (e.g., "GitHub Repository"), the link may not be re-inserted.
- For best results, keep anchor texts for links unchanged in your resume.
- PDF conversion requires Microsoft Word. If it fails, open the tailored `.docx` and export as PDF manually.

---

## Customization

- To add support for more hyperlinks (e.g., LinkedIn), extend the `extract_github_link` and `add_hyperlink` logic.
- To tailor only specific sections, modify the `section_titles` list in the script.

---

## License

MIT License

---

## Acknowledgements

- [python-docx](https://python-docx.readthedocs.io/)
- [docx2pdf](https://github.com/AlJohri/docx2pdf)
- [Google Generative AI](https://ai.google.dev/)
