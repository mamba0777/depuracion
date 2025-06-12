# depuracion


import 'package:flutter/material.dart';

void main() { runApp(const MyApp()); }

class MyApp extends StatelessWidget { const MyApp({Key? key}) : super(key: key);

@override Widget build(BuildContext context) { return MaterialApp( title: 'Flutter Debug Example', theme: ThemeData( primarySwatch: Colors.blue, ), home: const MyHomePage(), debugShowCheckedModeBanner: false, // Oculta la bandera de "Debug" ); } }

class MyHomePage extends StatefulWidget { const MyHomePage({Key? key}) : super(key: key);

@override _MyHomePageState createState() => _MyHomePageState(); }

class _MyHomePageState extends State { int _counter = 0;

void _incrementCounter() { setState(() { _counter++; debugPrint('Contador incrementado: $_counter'); // Imprime en consola para depuración }); }

@override void initState() { super.initState(); debugPrint('Inicializando el estado de MyHomePage'); // Log al iniciar }

@override Widget build(BuildContext context) { return Scaffold( appBar: AppBar( title: const Text('Flutter Debug Example'), ), body: Center( child: Column( mainAxisAlignment: MainAxisAlignment.center, children: [ const Text( 'Has presionado el botón esta cantidad de veces:', ), Text( '$_counter', style: Theme.of(context).textTheme.headlineMedium, ), ], ), ), floatingActionButton: FloatingActionButton( onPressed: _incrementCounter, tooltip: 'Incrementar', child: const Icon(Icons.add), ), ); } }
