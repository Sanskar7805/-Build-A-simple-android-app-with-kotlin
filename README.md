"# -Build-A-simple-android-app-with-kotlin" 
package com.example.myapplication

import android.app.Application
import androidx.appcompat.app.AppCompatActivity
import android.os.Bundle
import androidx.recyclerview.widget.LinearLayoutManager

private var Any.adapter: ApplicationAdapter


class MainActivity : AppCompatActivity() {

    private val btnDeleteDoneApplications: Any
    private var rvApplicationItems: Any
    private lateinit var applicationAdapter: ApplicationAdapter
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        applicationAdapter = ApplicationAdapter(mutableListOf())
        
        rvApplicationItems.adapter = applicationAdapter
        rvApplicationItems.layoutManager = LinearLayoutManager(this)

        btnAddApplication.setOnClickListener {
            val applicationTitle = etApplicationTitle.text.toString()
            if(applicationTitle.isNotEmpty()) {
                val application = Application(applicationTitle) 
                applicationAdapter.addApplication(application)
                etApplicationTitle.text.clear()
            }
        }
        btnDeleteDoneApplications. {
applicationAdapter.deleteDoneApplications()
        }
    }
}


<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="TextView"
        tools:layout_editor_absoluteX="0dp"
        tools:layout_editor_absoluteY="5dp" />

    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/rvMyApplicationItems"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="88dp"

        app:layout_constraintTop_toTopOf="parent"
        tools:layout_editor_absoluteX="25dp" />

    <EditText
        android:id="@+id/etMyApplicationTitle"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginBottom="4dp"
        android:hint="Enter MyApplication Title"
        app:layout_constraintBottom_toBottomOf="parent"
        tools:layout_editor_absoluteX="0dp" />

    <Button
        android:id="@+id/btnAddApplication"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:layout_marginBottom="4dp"
        android:text="Add MyApplication"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.048"
        app:layout_constraintStart_toEndOf="@+id/etMyApplicationTitle" />

    <Button
        android:id="@+id/btnDeleteApplication"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:layout_marginBottom="4dp"
        android:text="Delete Done"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.788"
        app:layout_constraintStart_toEndOf="@+id/etMyApplicationTitle" />

</androidx.constraintlayout.widget.ConstraintLayout />

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="TextView"
        tools:layout_editor_absoluteX="0dp"
        tools:layout_editor_absoluteY="5dp" />

    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/rvMyApplicationItems"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="88dp"

        app:layout_constraintTop_toTopOf="parent"
        tools:layout_editor_absoluteX="25dp" />

    <EditText
        android:id="@+id/etMyApplicationTitle"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginBottom="4dp"
        android:hint="Enter MyApplication Title"
        app:layout_constraintBottom_toBottomOf="parent"
        tools:layout_editor_absoluteX="0dp" />

    <Button
        android:id="@+id/btnAddApplication"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:layout_marginBottom="4dp"
        android:text="Add MyApplication"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.048"
        app:layout_constraintStart_toEndOf="@+id/etMyApplicationTitle" />

    <Button
        android:id="@+id/btnDeleteApplication"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginEnd="32dp"
        android:layout_marginBottom="4dp"
        android:text="Delete Done"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.788"
        app:layout_constraintStart_toEndOf="@+id/etMyApplicationTitle" />

</androidx.constraintlayout.widget.ConstraintLayout />

package com.example.myapplication

 data class MyApplication (
     val title: String,
             var isChecked: Boolean = false
 )
 
 package com.example.myapplication

import android.app.Application
import android.graphics.Paint.STRIKE_THRU_TEXT_FLAG
import android.icu.text.CaseMap
import android.view.LayoutInflater
import android.view.View
import android.view.ViewGroup
import android.widget.CheckedTextView
import android.widget.TextView
import androidx.recyclerview.widget.RecyclerView
import java.nio.file.Files.size

private fun Any.setOnCheckedChangeListener(any: Any) {

}
private var Any.isChecked: Any
    get() {}
    set() {}
private var Any.text: Any
    get() {}
    set() {}
private val Application.title: Any
    get() {}
private val Application.isChecked: Any
    get() {}

class ApplicationAdapter (
    private val applications: MutableList<Application>
) : RecyclerView.Adapter<ApplicationAdapter.ApplicationViewHolder>() {
    private val cbDone: Any
    private val tvApplicationTitle: Any

    class ApplicationViewHolder(itemView:View) : RecyclerView.ViewHolder(itemView)

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ApplicationViewHolder {
       return ApplicationViewHolder(
           LayoutInflater.from(parent.context).inflate(
               R.layout.item_todo,
               parent,
               false

           )
       )
    }
    fun addApplication(application: Application) {
        applications.add(application)
        notifyItemInserted(applications.size-1)
    }
    fun deleteDoneApplications() {
        applications.removeAll { application ->
            application.isChecked
        }
        notifyDataSetChanged()
    }

    private fun togglesStrikeThrough(tvApplicationTitle: TextView,isChecked:Boolean) {
        if(isChecked) {
            tvApplicationTitle.paintFlags = tvApplicationTitle or STRIKE_THRU_TEXT_FLAG
        } else {
            tvApplicationTitle.paintFlags and STRIKE_THRU_TEXT_FLAG.inv()
        }
    }

    override fun onBindViewHolder(holder: ApplicationViewHolder, position: Int) {
       val curApplication = applications[position]

         holder.itemView.apply {
            tvApplicationTitle.text = curApplication.title
             cbDone.isChecked = curApplication.isChecked
             togglesStrikeThrough(tvApplicationTitle: TextView, curApplication.isChecked:Boolean)
            cbDone.setOnCheckedChangeListener {_, isChecked ->
                togglesStrikeThrough(tvApplicationTitle: TextView,isChecked:Boolean)
                curApplication.isChecked = !curApplication.isChecked
            }

        }

    }

    override fun getItemCount(): Int {
     return   applications.size
    }
}


package com.example.myapplication

import android.app.Application
import android.graphics.Paint.STRIKE_THRU_TEXT_FLAG
import android.icu.text.CaseMap
import android.view.LayoutInflater
import android.view.View
import android.view.ViewGroup
import android.widget.CheckedTextView
import android.widget.TextView
import androidx.recyclerview.widget.RecyclerView
import java.nio.file.Files.size

private fun Any.setOnCheckedChangeListener(any: Any) {

}
private var Any.isChecked: Any
    get() {}
    set() {}
private var Any.text: Any
    get() {}
    set() {}
private val Application.title: Any
    get() {}
private val Application.isChecked: Any
    get() {}

class ApplicationAdapter (
    private val applications: MutableList<Application>
) : RecyclerView.Adapter<ApplicationAdapter.ApplicationViewHolder>() {
    private val cbDone: Any
    private val tvApplicationTitle: Any

    class ApplicationViewHolder(itemView:View) : RecyclerView.ViewHolder(itemView)

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ApplicationViewHolder {
       return ApplicationViewHolder(
           LayoutInflater.from(parent.context).inflate(
               R.layout.item_todo,
               parent,
               false

           )
       )
    }
    fun addApplication(application: Application) {
        applications.add(application)
        notifyItemInserted(applications.size-1)
    }
    fun deleteDoneApplications() {
        applications.removeAll { application ->
            application.isChecked
        }
        notifyDataSetChanged()
    }

    private fun togglesStrikeThrough(tvApplicationTitle: TextView,isChecked:Boolean) {
        if(isChecked) {
            tvApplicationTitle.paintFlags = tvApplicationTitle or STRIKE_THRU_TEXT_FLAG
        } else {
            tvApplicationTitle.paintFlags and STRIKE_THRU_TEXT_FLAG.inv()
        }
    }

    override fun onBindViewHolder(holder: ApplicationViewHolder, position: Int) {
       val curApplication = applications[position]

         holder.itemView.apply {
            tvApplicationTitle.text = curApplication.title
             cbDone.isChecked = curApplication.isChecked
             togglesStrikeThrough(tvApplicationTitle: TextView, curApplication.isChecked:Boolean)
            cbDone.setOnCheckedChangeListener {_, isChecked ->
                togglesStrikeThrough(tvApplicationTitle: TextView,isChecked:Boolean)
                curApplication.isChecked = !curApplication.isChecked
            }

        }

    }

    override fun getItemCount(): Int {
     return   applications.size
    }
}


<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="80dp"
    android:paddingStart="8dp"
    android:paddingEnd="8dp">


    <TextView
        android:id="@+id/tvTodoTitle"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginStart="16dp"
        android:text="Example"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toStartof="@+id/cbDone"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.666" />

    <CheckBox
        android:id="@+id/cbDone"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintsBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintTop_toTopOf="parent"/>


</androidx.constraintlayout.widget.ConstraintLayout>
