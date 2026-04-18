<html><head></head><body><h1>Telegram Chat + Media Viewer in HTML</h1>
<p>

<img width="764" height="759" alt="Image" src="https://github.com/user-attachments/assets/de35c333-d02d-4207-b05f-e98776f0307e" />

. Load your CSV export and media files to replay any conversation in a chat interface with media viewer. — entirely offline, with no server or installation required.</p>
<hr>
<h2>Features</h2>
<ul>
<li><strong>Chat bubble UI</strong> — messages rendered as sent/received bubbles with per-sender colour coding, timestamps, and date separators</li>
<li><strong>Full media support</strong> — inline display of images, videos, GIFs, audio players, stickers, and downloadable file attachments</li>
<li><strong>Lightbox viewer</strong> — click any image or video to open a fullscreen viewer with prev/next navigation and keyboard controls</li>
<li><strong>Message search</strong> — live filtering by message text or sender name, with highlighted matches</li>
<li><strong>Stats bar</strong> — summary of total messages, participant count, media count, and conversation date range</li>
<li><strong>Missing media handling</strong> — graceful placeholder shown when a media file wasn't loaded, without breaking the rest of the chat</li>
<li><strong>Jump to bottom</strong> — floating button appears when scrolled up, returns to the latest message instantly</li>
<li><strong>Zero dependencies</strong> — pure HTML/CSS/JS, no frameworks, no network requests, no data leaves your device</li>
</ul>
<hr>
<h2>Requirements</h2>
<ul>
<li>A modern web browser (Chrome, Firefox, Safari, Edge)</li>
<li>An exported Telegram chat in CSV format</li>
</ul>
<hr>
<h2>How to Export from Telegram Desktop</h2>
<ol>
<li>Open the chat you want to export</li>
<li>Click the <strong>⋮ menu</strong> (top-right) → <strong>Export chat history</strong></li>
<li>Set the format to <strong>CSV</strong> (or Machine-readable JSON — CSV is recommended)</li>
<li>Enable <strong>Include media</strong> to export photos, videos, and other files</li>
<li>Click <strong>Export</strong></li>
</ol>
<p>The result will be a folder containing:</p>
<ul>
<li><code>result.csv</code> (or similar) — the messages file</li>
<li>Subfolders such as <code>photos/</code>, <code>video/</code>, <code>voice_messages/</code>, <code>files/</code>, etc.</li>
</ul>
<hr>
<h2>Usage</h2>
<ol>
<li>Open <code>telegram_viewer.html</code> in your browser (double-click or drag into a browser tab)</li>
<li>On the upload screen, click <strong>Chat CSV</strong> and select your exported <code>.csv</code> file</li>
<li>Click <strong>Media Files</strong> and select all files from the export's media subfolders (you can select files from multiple folders in one go using your OS file picker)</li>
<li>Click <strong>Open Chat →</strong></li>
</ol>
<p>The chat will load and scroll to the most recent message.</p>
<blockquote>
<p><strong>Media is optional.</strong> You can load the CSV alone — messages will display normally, and any media references will show a "file not loaded" placeholder instead.</p>
</blockquote>
<hr>
<h2>Supported CSV Columns</h2>
<p>The viewer uses flexible column name matching and will recognise common variations automatically. The following fields are detected:</p>

Field | Recognised column names
-- | --
Date/time | date, datetime, timestamp, time, created_at, sent_at
Sender | from, sender, author, name, from_name, user, from_username
Message text | message, text, body, content, msg, caption
Media filename | filename, filepath, file_name, file, photo, attachment
Media type | media_type, document_type, kind, message_type
Message ID | message_id, id, msg_id


<hr>
<h2>Privacy</h2>
<p>All processing happens locally in your browser. No files are uploaded anywhere. Closing or refreshing the page clears everything.</p>
<hr>
<h2>Limitations</h2>
<ul>
<li>Exported Telegram CSVs do not always include full media paths; if filenames in the CSV don't match the actual filenames, media will show as "not loaded"</li>
<li>Very large exports (tens of thousands of messages) may take a moment to render</li>
<li>The viewer identifies the first sender in the CSV as "you" (displayed on the right); this works correctly for direct exports but may need adjustment for forwarded or group-only exports</li>
</ul></body></html>
