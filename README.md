https://github.com/python-poetry/poetry/issues/3459

```bash
diff --git a/src/poetry/utils/env.py b/src/poetry/utils/env.py
index 8d897fd2..d885c33e 100644
--- a/src/poetry/utils/env.py
+++ b/src/poetry/utils/env.py
@@ -1209,9 +1209,9 @@ class EnvManager:
         sanitized_name = re.sub(r'[ $`!*@"\\\r\n\t]', "_", name)[:42]
         normalized_cwd = os.path.normcase(os.path.realpath(cwd))
         h_bytes = hashlib.sha256(encode(normalized_cwd)).digest()
-        h_str = base64.urlsafe_b64encode(h_bytes).decode()[:8]
+        # h_str = base64.urlsafe_b64encode(h_bytes).decode()[:8]
 
-        return f"{sanitized_name}-{h_str}"
+        return f"{sanitized_name}"
```