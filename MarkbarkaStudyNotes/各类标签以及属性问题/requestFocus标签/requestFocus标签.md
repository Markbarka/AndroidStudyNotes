# requestFocus标签

标签（空格分隔）： Android

---

标签用于指定屏幕内的焦点View。
例如我们点击tab键或enter键焦点自动进入下一个输入框
用法: 将标签置于Views标签内部

            <EditText id="@+id/text"
                         android:layout_width="fill_parent"
                         android:layout_height="wrap_content"
                         android:layout_weight="0"
                         android:paddingBottom="4">
                   <requestFocus />
            </EditText>




