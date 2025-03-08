# alert-imessage
Alert message custom on bootstrap 5.3

# Example calls JS
// imessage.show("Default Success!", "success");
// imessage.show("Top Center Message!", "info", "top-center");
// imessage.show("Bottom Right Warning!", "warning", "bottom-right");
// imessage.show("Bottom Left Error!", "fail", "bottom-left");
// imessage.show("Centered Notification!", "info", "center");

# Example calls in Laravel
 return redirect()->back()->with('success', 'Default Success!');
 return redirect()->back()->with('error', 'Default Error!');
 return redirect()->back()->with('info', 'Default Info!');
 return rredirect()->back()->with('warning', 'Default Warning!');

# Example calls in Laravel on main page
<script>
    document.addEventListener("DOMContentLoaded", function () {
        let messages = {
            success: "{{ session('success') }}",
            error: "{{ session('error') }}",
            warning: "{{ session('warning') }}",
            info: "{{ session('info') }}"
        };

        Object.keys(messages).forEach(type => {
            if (messages[type]) {
                new Message('imessage').show(messages[type], type === "error" ? "fail" : type, "top-center");
            }
        });
    });
</script>
