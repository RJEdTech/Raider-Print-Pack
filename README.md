# Raider Print Pack

Print a whole Canvas assignment or New Quiz at once: one PDF, one student per page. Built for Regis Jesuit High School.

**Live site:** https://rjedtech.github.io/Raider-Print-Pack/

## What it does

- **New Quizzes:** reads the quiz's *Student Analysis* report (Reports tab → Generate Report → Export CSV) and lays out every student's essay answers, one student per page, with name, class period and time submitted. Sorted by class period, then last name.
- **Assignments with file uploads:** reads the `.zip` from *Download Submissions* and combines Word documents (`.docx`), PDFs, photos and online text entries into one PDF. Anything else (Pages files, Google links, video) is listed as *Print by hand*.
- Optional student name on every page, and a blank page between students for double-sided printing.
- **Print** opens the browser's print window directly; **Save PDF instead** downloads the file.
- Runs entirely in the browser. Student work never leaves the teacher's computer.

## How it's built

One self-contained `index.html`, plus screenshots in `img/`. Libraries load from cdnjs and jsDelivr:

| Library | Use |
|---|---|
| JSZip 3.10.1 | read the Download Submissions zip |
| pdf-lib 1.17.1 | build the combined PDF, copy in student PDFs |
| html2canvas 1.4.1 | turn essays, text entries and Word pages into page images |
| docx-preview 0.4.1 | render `.docx` in the browser |

Long answers are cut into pages only at blank rows of pixels, so no line of text is split across two pages.

## Known limits

- New Quizzes: only essay-question answers are printed. File-upload questions inside a New Quiz are not supported.
- Images pasted inside a New Quiz essay are hosted by Canvas and can't be fetched, so they're left out.
- Word documents are re-drawn in the browser. A font the computer doesn't have is substituted.

## Screenshots

The step-by-step screenshots come from a real RJ Canvas course with student names cropped out. Retake them if Canvas moves the buttons.
