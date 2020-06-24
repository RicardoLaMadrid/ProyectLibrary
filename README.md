# ProyectLibrary
Proyecto para la materia de SOME
para importar la libreria 
Primero debemos copiar el siguiente link en los repositorios del proyecto

allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
Segundo debemos copiar el siguiente link en las dependencias de la app
  
  dependencies {
	        implementation 'com.github.RicardoLaMadrid:ProyectLibrary:Tag'
	}
  
para implementar la libreria debemos copiar el siguiente codigo en el MainActivity


public class MainActivity extends AppCompatActivity {

    private ViewPager viewPagerContainer;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        _initializeComponents();

        //initializeAdapter
        _initializeFragmentAdapter();
    }
    public void _initializeComponents()
    {
        viewPagerContainer = findViewById(com.example.libraryonboarding.R.id.viewPagerContainer);
    }

    public void _initializeFragmentAdapter()
    {
        OnboardingAdapter adapter = new OnboardingAdapter(getSupportFragmentManager());
        viewPagerContainer.setAdapter(adapter);
    }
}


y por ultimo copir el siguiente codigo en el archivo XML

<androidx.viewpager.widget.ViewPager
       android:id="@+id/viewPagerContainer"
       android:layout_width="match_parent"
       android:layout_height="match_parent">
   </androidx.viewpager.widget.ViewPager>
